接口服务器URL:

http://192.168.1.250/dailyapp

要求:

​	程序调用的时候一律使用post提交，目前开放get和post，之后只开放post

调用格式(get的方式):

​	 接口服务器url+接口+参数字符串

调用范例:

​	http://192.168.1.250:8080/dailyapp/login?loginName=chenyan&password=123456	

	接口通用标准和说明
	{	
		"message":返回信息
		 "status":状态  200 说明是符合业务规范并能正常运作的，其余的值都是不正常的
		  "data": 
		  {
	          数据内容
	       }
	 } 
​       

1. 用户登录

   接口地址:  /login

   参数：

| 参数名称      | 参数意义 | 参数类型 | 参数格式 | 范例      | 是否必输 |
| :-------- | :--- | :--- | :--- | :------ | :--- |
| loginName | 登录名  | 字符串  |      | chenyan | 是    |
| password  | 登录密码 | 字符串  |      | 123456  | 是    |

	返回json字符串及说明:

	{
	    "data": 
	    	{
	          "id": 1,  // 用户id
	          "name": "陈严", //用户姓名
	          "sex": "1", // 用户性别 0:女 1:男
	          "birthday": "2016-09-29", // 用户生日 yyyy-MM-dd
	          "password": "123456", // 用户密码
	          "description": null, // 用户描述
	          "loginName": "chenyan" // 登录账号
	        },
	    "message": "登录成功",
	    "status": "200"
	}


2. 用户注册

   接口地址:  /register

   参数：

|      参数名称       |  参数意义  | 参数类型 |    参数格式    |     范例     | 是否必输 |
| :-------------: | :----: | :--: | :--------: | :--------: | :--: |
|    loginName    |  登录名   | 字符串  |            |  chenyan   |  是   |
|    password     |  登录密码  | 字符串  |            |   123456   |  是   |
| confirmPassword | 确认密码密码 | 字符串  |            |   123456   |  是   |
|    birthday     |  出生日期  | 字符串  | yyyy-MM-dd | 1990-08-09 |  是   |
|   description   |  用户描述  | 字符串  |            |    阿斯蒂芬    |  否   |

​    返回json字符串及说明:

	{
		"data": 
			{
			"id": 1476693149018, // 用户id
			"name": "测试账号", // 用户姓名
			"sex": "1", // 用户姓名 0:女 1:男
			"birthday": "1990-09-04", // 用户生日
			"password": "123456", // 用户密码
			"description": "11", // 用户描述
			"loginName": "test" // 登录账号
			},
		"message": "新增成功",
		"status": "200"
	}