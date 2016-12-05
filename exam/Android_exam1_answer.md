1.C

​	解析：

​	A：对，startActivity，startService，sendBroadcastReceiver等等

​	B:对，本意就是一个意图

​	C:错，同一个app中不同组件之间传递信息

​	D:对。



2.A

​	解析：

​	A andriod提供了 Handler  和  Looper  来满足线程间的通信。 Handler 先进先出原则。 Looper 类用来管理特定线程内对象之间的消息交换 (MessageExchange) 。  

1) Looper:  一个线程可以产生一个 Looper 对象，由它来管理此线程里的 MessageQueue( 消息队列 ) 。  
2) Handler:  你可以构造 Handler 对象来与 Looper 沟通，以便 push 新消息到 MessageQueue 里 ; 或者接收 Looper 从Message Queue 取出 ) 所送来的消息。  
3) Message Queue( 消息队列 ): 用来存放线程放入的消息。  
4) 线程： UIthread  通常就是 main thread ，而 Android 启动程序时会替它建立一个 MessageQueue 。 



3.D

​	解析：

​	解释：A、C很明显是android 动画的两种类型，而

​	B属于Tween动画的一种。

​	Tween（渐变动画）包含：alpha和scale

​	Frame（画面转换动画）包含：translate和rotate



4.B

​	解析：

​	Intent.ACTION_VIEW

​	String android.intent.action.VIEW

​	用于显示用户的数据。比较通用，会根据用户的数据类型打开相应的Activity。

​	比如 tel:13400010001打开拨号程序，[http://www.g.cn](http://www.g.cn/)则会打开浏览器等。

​	例如：

​		Uri uri = Uri.parse("http://www.google.com"); //浏览器(网址必须带http) //

​		Uri uri =Uri.parse("tel:1232333");              //拨号程序 //Uri 		      			   uri=Uri.parse("geo:39.899533,116.036476");          //打开地图定位 

Intent it  = new Intent(Intent.ACTION_VIEW,uri);  //Intent.ACTION_VIEW不带引号startActivity(it);



5.A

​	解析：

​	xml命名可以是小写字母、数字、下划线



6.D

​	解析：

​	key值应该是一个随便什么样的字符串，value值可以是序列化之后的对象。



7.A

​	解析：

​	Android中不允许开启一个新新线程更新UI，所以BD错误

​	C Handler采用的是消息队列的方式，每一个Handler都会有一个与之相关联的消息队列，而且都是以先进先出的方式执行



8.C

​	解析：

​	略



9.D

​	解析：查查API和相关demo

​	A:show()方法最终还是创建并显示。

​	B：查看源码，正确；

​	C:因为其构造器都是保护的，所以不允许非子类调用；

​	D:create()方法只创建，不显示；



10.D

​	解析：

​	<!-- 发送消息-->
​	< uses-permission android:name="android.permission.SEND_SMS"/>
​	< !-- 阅读消息-->
​	< uses-permission android:name="android.permission.READ_SMS"/>
​	< !-- 写入消息-->
​	< uses-permission android:name="android.permission.WRITE_SMS" />
​	< !-- 接收消息 -->
​	< uses-permission android:name="android.permission.RECEIVE_SMS" />



11.D

​	解析：

​	**RadioButton和CheckBox的区别：**

​	1、单个RadioButton在选中后，通过点击无法变为未选中

​	    单个CheckBox在选中后，通过点击可以变为未选中

​	2、一组RadioButton，只能同时选中一个

​	     一组CheckBox，能同时选中多个

​	3、RadioButton在大部分UI框架中默认都以圆形表示

​	     CheckBox在大部分UI框架中默认都以矩形表示

​	**RadioButton和RadioGroup的关系：**

​	1、RadioButton表示单个圆形单选框，而RadioGroup是可以容纳多个RadioButton的容器

​	2、每个RadioGroup中的RadioButton同时只能有一个被选中

​	3、不同的RadioGroup中的RadioButton互不相干，即如果组A中有一个选中了，组B中依然可以有一个被选中

​	4、大部分场合下，一个RadioGroup中至少有2个RadioButton

​	5、大部分场合下，一个RadioGroup中的RadioButton默认会有一个被选中，并建议您将它放在RadioGroup中的起始位置



12.BD

​	解析：

​	RemoteView描述一个view,而这个view是在另外一个进程显示的。它inflate于layout资源文件。并且提供了		可以修改过view内容的一些简单基础的操作。  

**从这个定义我们就知道RemoteView是用来描述一个垮进程显示的view**。 从而你就会明白为什么AppWidget和Nofication需要用到它了。 **http://blog.csdn.net/qaz13177_58_/article/details/7497944**



13.BD

​	解析：

​	Android数据持久化有五种方式：

​	1、SharedPreferences

​	2、内部存储（例如通过openFileOutput()打开一个文件输入输出流）

​	3、SQLite Database

​	4、网络连接（将数据存储到服务器上）

​	5、外部存储（SD卡）



14.AC

​	解析：

​	在Android上，如果你的应用程序有一段时间响应不够灵敏，系统会向用户显示一个对话框，这个对话框称作应用程序无响应（ANR：Application Not Responding）对话框。用户可以选择“等待”而让程序继续运行，也可以选择“强制关闭”。



​	ANR(Application Not Responding)定义

     在Android上，如果你的应用程序有一段时间响应不够灵敏，系统会向用户显示一个对话框，这个对话框称作应用程序无响应ANR。用户可以选择“等待”而让程序继续运行，也可以选择“强制关闭”。默认情况下，在android中Activity的最长执行时间是5秒，BroadcastReceiver的最长执行时间则是10秒

默认情况下，在android中Activity的最长执行时间是5秒，BroadcastReceiver的最长执行时间则是10秒。超出就会提示应用程序无响应（ANR：Application Not Responding）对话框。

三种常见类型

**1：** **KeyDispatchTimeout(5 seconds) --** **主要类型**

按键或触摸事件在特定时间内无响应

**2** **：** **BroadcastTimeout(10 seconds)**

BroadcastReceiver在特定时间内无法处理完成

**3：** **ServiceTimeout(20 seconds) --** **小概率类型**

Service在特定的时间内无法处理完成



UI线程阻塞时间超过5s会ANR，广播阻塞时间超过10s会ANR



15.ABD

​	解析：

​		theme是被final标示的，不能被继承。而且，xml文件中的parent不属于继承。说一下xml文件的解析规则。遇到parent就取parent里面解析，逐个递归，最后解析自己，相同的元素会被后面解析出来的覆盖吊



16.AC

​	解析：

​	上下文菜单（通过在某元素上长按，来呼出菜单） 
选项菜单（通过按手机上的菜单按钮，来呼出菜单）   

重写 onCreateContextMenu 用以创建上下文菜单 
重写 onContextItemSelected 用以响应上下文菜单  

重写 onCreateOptionsMenu 用以创建选项菜单 
重写 onOptionsItemSelected 用以响应选项菜单 

当每次Menu显示时，会调用方法onPrepareOptionsMenu，也可以在菜单每次被调用时，对菜单中的项重新生成，通过重载onPrepareOptionsMenu来实现,由于每次调用时都要重新生成，对于那些不经常变化的菜单，效率就会比较低。 

调用Menu.addSubMenu()方法，为某个菜单项添加子菜单

​	android中有三种菜单

（1）选项菜单Options menus :一个Activity只能有一个选项菜单，在按下Menu键时，显示在屏幕下方。

（2）上下文菜单Context menus :为Activity中的任何一个视图注册一个上下文菜单，“长按”出现。

（3）弹出式菜单Popup menus :依赖于Activity中的某个一个视图。



17.BC

​	解析：

​	A 设置Activity的android:screenOrientation="portrait"属性时,无法切换横竖屏，因此不但不会重新调用各个生命周期方法，而且onConfigurationChanged()方法也不会执行。 **

​	B 未设置Activity的android:configChanges属性，API上这样说"the activity will be restarted if any of these configuration changes happen in the system.";如何配置有改变，就会重启activity 

​	C launchMode为singleTask的时候，通过Intent启到一个Activity, 如果系统已经存在一个实例，系统就会将请求发送到这个实例上，但这个时候，系统就不会再调用通常情况下我们处理请求数据的onCreate方法，而是调用onNewIntent方法

​	 D 用户正在操作某个Activity，这时如果其他应用程序需要内存。 此时的Activity是Foreground process,应该按照Empty process，Background process，Service process，Visible process顺序kill，最后才是前台进程。



18.ACD

​	解析：

​		根据SimpleAdapter的源码可以知道，使用SimpleAdapter作为适配器是，会按照如下顺序判断View:

​		1、该view是否实现checkable接口 

​		2、该view是否是TextView 

​		3、该view是否是ImageView 

​		如果以上三种类型都不是，就会抛出IllegalStateExeception



19.BD

​	解析：可查看API

​		Toast是Android中用来显示显示信息的一种机制，和Dialog不一样的是，Toast是没有焦点的，而且		Toast显示的时间有限，过一定的时间就会自动消失。  Toast也可以完全自定义，还可以带图片



20.ABCD

​	解析：

​		Intent可以传递哪些类型的数据

1. 8种基本数据类型及其数组 


2. String（String实现了 Serializable ）/CharSequence实例类型的数据及其数组 
3. 实现了Parcelable的对象及其数组 
4. 实现了 Serializable 的对象及其数组 


21.A

​	解析:

​		//实例化SharedPreferences对象（第一步） 
SharedPreferences mySharedPreferences= getSharedPreferences(``"test"``, ``Activity.MODE_PRIVATE); 

//实例化SharedPreferences.Editor对象（第二步）

(android.content.SharedPreferences.Editor)
SharedPreferences.Editor editor = mySharedPreferences.edit(); 

//用putString的方法保存数据 
editor.putString("name", "Karl"); editor.putString("habit", "sleep"); 

//提交当前数据 
editor.commit();



22.A

​	解析：

​	scaleType：设置图片的填充方式 

​	adjustViewBounds：调整边框时是否保持可绘制对象的宽高比 

​	用src来设置要展示的图片 主要在布局文件里配置



23.A

​	解析：

​	在创建的时候 我们肯定会设置分辨率 和 内存大小 所以BC正确 D项我们在创建的时候 也会设置其支持 除此之外 还有键盘支持 而没有蓝牙支持 所以选A



24.A

​	解析：

​	略



25.A

​	解析：

​	onSaveInstanceState() 
当你的程序中某一个Activity A在运行时，主动或被动地运行另一个新的Activity B，这个时候A会执行onSaveInstanceState()。B完成以后又会来找A，这个时候就有两种情况：一是A被回收，二是A没有被回收，被回收的A就要重新调用onCreate()方法，不同于直接启动的是这回onCreate()里是带上了参数savedInstanceState；而没被收回的就直接执行onResume()，跳过onCreate()了。



26.AB

​	解析：

​	略



27.B



28.A



29.C



30.C

​	解析：

​	**dip: device independent pixels(设备独立像素).**  不同设备有不同的显示效果,这个和设备硬件有关，一般我们为了支持WVGA、HVGA和QVGA 推荐使用这个，不依赖像素。 

        **px: pixels(像素).**  不同设备显示效果相同，一般我们HVGA代表320x480像素，这个用的比较多。 
      	pt: point ，是一个标准的长度单位，1pt＝1/72英寸，用于印刷业，非常简单易用； 
        **sp: scaled pixels(放大像素).**  主要用于字体显示best for textsize。由此，根据 google 的建议，TextView 的 
字号最好使用 sp 做单位，而且查看TextView的源码可知 Android 默认使用 sp 作为字号单位。



31.AC

​	解析：

​	AD：产生ANR，程序没有响应，有可能程序会再次响应

​	BC：程序抛出异常，会强制退出



32.ABCD

​	解析：

​	如果listview只是一种类型，那么只需要重写a，和getview()即可，但是这里已经写明了，有imageview和textview，所以需要b来得到当前的view id号，和c得到当前view的类型 至于最后一个也是需要的，这些方法都是非常有必要的。



33.A

​	解析：

​	ContentResolver和 ContentProvider是一对。一个运行在提供数据端(provider),一个运行在调用端(resolver)。使用的时候利用resolver来调用provider的方法(query,insert,update等)，然后provider再进行数据查询 
    Cursor是游标，返回结果集的。provider的query可以返回这中类型的结果。

    SQliteHelper这个应该是干扰项，我记得是SQLiteOpenHelper啊。管理数据库的，一般继承它，然后重写onCreate、onUpGrade



34.A

​	解析：

​	一般的常规写法，在activity结束时，应当一并把有关线程都销毁，因此在onDestroy里调用线程的removeCallbacks。但仔细一看，其实 removeCallbacks调用的就是线程的stop方法

​	线程的销毁

Hanlder是线程与Activity通信的桥梁,利用handler接收到任务线程，放到任务队列里面派对执行。

//调用该任务线程的run() 方法执行任务线程。

Handler updateBarHandler =new handler();
handler.post(Runnable Thread);

//移除handler里的任务线程,调用线程的stop()方法，销毁线程。
handler.removecallbacks(Runnable Thread);

一个简单的例子如下:
import Android.app.Activity; 
import Android.os.Bundle; 
import Android.os.Handler; 
import Android.util.Log; 
public class HandlerThread extends Activity { 
    private static final String TAG = "HandlerThread"; 
    private Handler mHandler =  new Handler(); 
    private Runnable mRunnable = new Runnable() { 
        public void run() { 
            Log.e(TAG, Thread.currentThread().getName() + "Thread run");         
        } 
    }; 
    @Override
    public void onCreate(Bundle savedInstanceState) { 
        super.onCreate(savedInstanceState); 
        setContentView(R.layout.main);  
        //通过Handler启动线程 
        mHandler.post(mRunnable); 
    } 
    @Override
    protected void onDestroy() { 
        //将线程销毁掉 
        mHandler.removeCallbacks(mRunnable); 
        super.onDestroy(); 
    } 
}



35.D

​	解析：

​	A, finish() 方法就是退出activity

B. actiivity中出现抛异常，会弹出框，强制退出当前activity的。

C. System.exit(0); 这是退出所有activity使用的。

D. onStop（） 只是activity一个周期方法，此时还没退出，只有走到onDestory（）才退出



36.A



37.D

​	解析：

​	Android2.2 以后的备份服务功能允许用户备份应用数据到云存储中，即当应用执行了工厂服务或转换到一个新的平台上时,如果备份的应用需要重新安装,系统就自动恢复原先备份的数据并重新安装。



38.D

​	解析：

​	重要性依次是：前台进程，可见进程，服务进程，后台进程和空进程；所以销毁的顺序是逆方向。

​	前台进程（foreground）： 目前正在屏幕上显示的进程和一些系统进程。举例来说，Dialer Storage，Google Search等系统进程就是前台进程；再举例来说，当你运行一个程序，如浏览器，当浏览器界面在前台显示时，浏览器属于前台进程（foreground），但一旦你按home回到主界面，浏览器就变成了后台程序（background）。 我们最不希望终止的进程就是前台进程。 可见进程（visible）： 可见进程是一些不在前台，但用户依然可见的进程，举个例来说：widget、输入法等，都属于visible。这部分进程虽然不在前台，但与我们的使用也密切相关，我们也不希望它们被终止（你肯定不希望时钟、天气，新闻等widget被终止，那它们将无法同步，你也不希望输入法被终止，否则你每次输入时都需要重新启动输入法） 次要服务（secondary server）： 目前正在运行的一些服务（主要服务，如拨号等，是不可能被进程管理终止的，故这里只谈次要服务），举例来说：谷歌企业套件，Gmail内部存储，联系人内部存储等。这部分服务虽然属于次要服务，但很一些系统功能依然息息相关，我们时常需要用到它们，所以也太希望他们被终止 后台进程（hidden）： 虽然用了hidden这个词，但实际即是后台进程（background），就是我们通常意义上理解的启动后被切换到后台的进程，如浏览器，阅读器等。当程序显示在屏幕上时，他所运行的进程即为前台进程（foreground），一旦我们按home返回主界面（注意是按home，不是按back），程序就驻留在后台，成为后台进程（background）。后台进程的管理策略有多种：有较为积极的方式，一旦程序到达后台立即终止，这种方式会提高程序的运行速度，但无法加速程序的再次启动；也有较消极的方式，尽可能多的保留后台程序，虽然可能会影响到单个程序的运行速度，但在再次启动已启动的程序时，速度会有所提升。这里就需要用户根据自己的使用习惯找到一个平衡点 内容供应节点（content provider）： 没有程序实体，仅仅提供内容供别的程序去用的，比如日历供应节点，邮件供应节点等。在终止进程时，这类程序应该有较高的优先权 空进程（empty）： 没有任何东西在内运行的进程，有些程序，比如BTE，在程序退出后，依然会在进程中驻留一个空进程，这个进程里没有任何数据在运行，作用往往是提高该程序下次的启动速度或者记录程序的一些历史信息。 这部分进程无疑是应该最先终止的。 补充： 系统会对进程的重要性进行评估，并将重要性以“oom_adj”这个数值表示出来，赋予各个进程；（系统会根据“oom_adj”来判断需要结束哪些进程，一般来说，“oom_adj”的值越大，该进程被系统选中终止的可能就越高） 前台程序的“oom_adj”值为0，这意味着它不会被系统终止，一旦它不可访问后，会获得个更高的“oom_adj”，推测“oom_adj”的值是根据软件在LRU列表中的位置所决定的； Android不同于Linux，有一套自己独特的进程管理模块，这个模块有更强的可定制性，可根据“oom_adj”值的范围来决定进程管理策略，比如可以设定“当内存小于X时，结束“oom_adj”大于Y的进程”。这给了进程管理脚本的编写以更多的选择。



39.B

​	解析：

​	android:capitalize 设置英文字母大写类型

​	android:singleLine 设置文本是否是一行显示，true:超出部分用...代替，false：会自动换行

​	android:text       设置文本内容



40.D

​	解析：

​	A：也可以在java文件中动态注册
B：可以在java文件中注销
C：也可以接受系统广播，比如网络状态改变等



41.B

​	解析：

​	A Base class for code that will receive intents sent by sendBroadcast(). API第一句话就说明了，用来接收广播发过来的Intent;所以A正确

​	B 明显错误，广播可以被订阅了该广播的所有接受者接收。

​	C The order receivers run in can be controlled with the android:priority attribute of the matching intent-filter; receivers with the same priority will be run in an arbitrary order.按照优先级别来执行。所以C正确

​	D Specify the relative importance or ability in handling a particular Intent. 正确



42.A

​	解析：

​	onCreate :表示Activity正在被创建。在这里可以做一些初始化的工作。

​	onRestart :表示Activity正在重新启动。当当前Activity从不可见重新变成可见状态。

​	onStart :表示Activity正在被启动。已经可见，但不在前台，无法交互。

​	onResume :表示Activity已经可见，并且出现在前台可以交互。

​	onPause :表示Activity正在停止。在这里可以做一些储存数据，停止动画等工作，**但不能太耗时**，因为必须onPause执行完成之后新的Activity才能Resume。

​	onStop :表示Activity即将停止。可以进行一些稍微重量级的回收工作，不能太耗时。

​	onDestroy :表示Activity即将被销毁。可以进行一些回收工作和最终的资源释放



43.BC



44.A

​	解析：

​	1.单选框操作：单选框在Android里面随处可见，它是由两部分组成的，一部分是RadioGroup，一部分是RadioButton。一个RadioGroup里面是有多个RadioButton。每个RadioButton就是一个单选项，而控制的时候是控制RadioGroup。

3.复选框(checkBox)：复选框就没有单选框那样有组的概念了，所以复选框的操作和单选框比起来就会比较复杂一点点，因为你要对每个复选框都进行一个事件响应。 

SeekBar是进度条



45.B

​	解析：

​	Uri的使用场景：

1，调web浏览器  
Uri myBlogUri = Uri.parse(" [http://xxxxx.com](http://xxxxx.com/) ");  
returnIt = new Intent(Intent.ACTION_VIEW, myBlogUri);  
2，地图  
Uri mapUri = Uri.parse("geo:38.899533,-77.036476");  
returnIt = new Intent(Intent.ACTION_VIEW, mapUri);  
3，调拨打电话界面  
Uri telUri = Uri.parse("tel:100861");  
returnIt = new Intent(Intent.ACTION_DIAL, telUri);  
4，直接拨打电话  
Uri callUri = Uri.parse("tel:100861");  
returnIt = new Intent(Intent.ACTION_CALL, callUri);  
5，卸载  
Uri uninstallUri = Uri.fromParts("package", "xxx", null);  
returnIt = new Intent(Intent.ACTION_DELETE, uninstallUri);  
6，安装  
Uri installUri = Uri.fromParts("package", "xxx", null);  
returnIt = new Intent(Intent.ACTION_PACKAGE_ADDED, installUri);  
7，播放  
Uri playUri = Uri.parse("file:///sdcard/download/everything.mp3");  
returnIt = new Intent(Intent.ACTION_VIEW, playUri);  
8，调用发邮件  
Uri emailUri = Uri.parse("mailto:xxxx@gmail.com");  
returnIt = new Intent(Intent.ACTION_SENDTO, emailUri);  
9，发邮件  
returnIt = new Intent(Intent.ACTION_SEND);  
String[] tos = { "xxxx@gmail.com" };  
String[] ccs = { "xxxx@gmail.com" };  
returnIt.putExtra(Intent.EXTRA_EMAIL, tos);  
returnIt.putExtra(Intent.EXTRA_CC, ccs);  
returnIt.putExtra(Intent.EXTRA_TEXT, "body");  
returnIt.putExtra(Intent.EXTRA_SUBJECT, "subject");  
returnIt.setType("message/rfc882");  
Intent.createChooser(returnIt, "Choose Email Client");  
10，发短信  
Uri smsUri = Uri.parse("tel:100861");  
returnIt = new Intent(Intent.ACTION_VIEW, smsUri);  
returnIt.putExtra("sms_body", "yyyy");  
returnIt.setType("vnd.android-dir/mms-sms");  
11，直接发邮件  
Uri smsToUri = Uri.parse("smsto://100861");  
returnIt = new Intent(Intent.ACTION_SENDTO, smsToUri);  
returnIt.putExtra("sms_body", "yyyy");  
12，发彩信  
Uri mmsUri = Uri.parse("content://media/external/images/media/23");  
returnIt = new Intent(Intent.ACTION_SEND);  
returnIt.putExtra("sms_body", "yyyy");  
returnIt.putExtra(Intent.EXTRA_STREAM, mmsUri);  
returnIt.setType("image/png");



46.A

​	解析：

​		显示时长只有2种设置

Toast.makeText(this, str, Toast.LENGTH_LONG).show();

toast只能设置为 2s和3.5s ，其它的值都无效，API的文档虽然写的第三个参数是时间，但是Framework里作了重定义，限定了 2s和3.5s 这两个值 ，对应 Toast.LENGTH_SHORT和Toast.LENGTH_LONG，实现方式在NotificationManagerService.java的scheduleTimeoutLocked()这个函数里。

Toast的默认显示时间有两个，分别为Toast.LENGTH_SHORT和Toast.LENGTH_LONG



47.C

​	解析：

​	1、首先会报错NullPointerException，就是privateButton mBtnLogin = (Button) findViewById(R.id.btn_login);这个位置，要先加载了layout后才能成功获取到相应的按钮组件对象；

2、修改NullPointerException错误后再运行，报错 Resources$NotFoundException，在mTextViewUser.setText(10);这个位置（原本以为会先检查onclick方法里的setText（），但实际是run（）里的setText（）），要改成字符串形式；

3、修改上面的错误后再运行，报错Resources$NotFoundException，这次就轮到mTextViewUser.setText(20);这个位置了；

4、修改上面的错误后再运行，没有报错，程序成功运行，点击按钮后TextView由10变为20，说好的不能在非UI线程里更新UI组件呢？翻看别人的博客后，终于找到答案了，其实非UI线程是可以刷新UI的，前提是它要拥有自己的ViewRoot，ViewRoot是在onResume（）里addview（）创建的，所以是在 onResume（）检查是否为UI线程，一般在onCreate（）中通过子线程可以更新UI，但官方不建议这样做，因为 Android UI操作并不是线程安全的。

PS：而且，可以试下在上面代码的run（）中setText（）前加一句Thread.sleep(2000)，先让线程休眠个2到3秒，就会报错ViewRootImpl$CalledFromWrongThreadException，说明已经检查到在非UI线程里更新UI。



48.ABCD

49.B

50.C

51、A
52、C
53、C
54、B
55、C
56、D
57、B
58、A
59、D
60、A
61、C
62、C
63、C
64、C
65、C
66、B
67、A
68、D
69、A
70、D 
71、D
72、C 
73、A
74、A

75、ABC
76、CD
77、AB
78、ABC
79、AB

80、B

81.D

82.D

83.B

84.B

85.D

86、B
87、B
88、A
89、D
90、B
91、C
92、A
93、B
94、D

95.CD

96、D
97、B
98、B
99、A

100、B



























​	



​	