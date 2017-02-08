emp 员工表
（empno 员工号
  ename 员工姓名
  job 工作
  mgr 上级编号
  hiredate 受雇日期
  sal 薪金
  comm 佣金
  deptno 部门编号）
　dept 部门表
　（deptno 部门编号
　dname 部门名称
　loc 地点）
　　工资 = 薪金 + 佣金
  1、列出至少有一个员工的所有部门。
  2、列出薪金比“SMITH”多的所有员工。（大于最大薪水SMITH员工）
  3、列出所有员工的姓名及其直接上级的姓名。
  4、列出受雇日期早于其直接上级的所有员工。
  5、列出部门名称和这些部门的员工信息，包括那些没有员工的部门。
  6、列出所有job为“CLERK”（办事员）的姓名及其部门名称。
  7、列出最低薪金大于1500的各种工作。
  8、列出在部门“SALES”（销售部）工作的员工的姓名，假定不知道销售部的部门编号。
  9、列出薪金高于公司平均薪金的所有员工。
  10、列出与“SCOTT”从事相同工作的所有员工。
  11、列出薪金等于部门30中员工的薪金的所有员工的姓名和薪金。
  12、列出薪金高于在部门30工作的所有员工的薪金的员工姓名和薪金。
  13、列出在每个部门工作的员工数量、平均工资和平均服务期限。
  14、列出所有员工的姓名、部门名称和工资。
  15、列出从事同一种工作但属于不同部门的员工的一种组合。
  16、列出所有部门的详细信息和部门人数。
  17、列出各种工作的最低工资。
  18、列出各个部门的MANAGER（经理）的最低薪金（job为MANAGER）。
  19、列出所有员工的年工资，按年薪从低到高排序。



第一步：建表：

create table dept(

       deptno number(10) primary key,

       dname varchar2(30),

       loc varchar2(30)

)

commit;

drop table emp;

drop table dept;

create table emp(

       empno number(10) primary key,

       ename varchar2(30),

       job varchar2(30),

       mgr varchar2(30),

       hiredate number(10),

       sal number(10),

       comm number(10),

       deptno number(10),

       foreign key(deptno) references dept(deptno)

)

　　第二步：向各表中插入数据：

insert into dept values(1, '技术部' ,'南泥湾');

insert into dept values(2, 'SALES' ,'深圳市');

insert into dept values(3, '事业部' ,'北京市');

insert into dept values(4, '服务部' ,'延安');

insert into dept values(5, '生产部' ,'南京市');

insert into dept values(6, '宣传部' ,'上海市');

insert into dept values(7, '打杂部' ,'广州市');

insert into dept values(8, '司令部' ,'重庆市');

insert into dept values(9, '卫生部' ,'长沙市');

insert into dept values(10, '文化部' ,'武冈市');

insert into dept values(11, '娱乐部' ,'纽约');

insert into dept values(12, '管理部' ,'伦敦');

insert into dept values(13, '行政部' ,'天津市');

select * from dept

insert into emp values(1, '关羽羽', 'CLERK' ,'刘备备', 20011109, 2000, 1000, 3);

insert into emp values(2, 'SMITH', 'CLERK' ,'刘备备', 20120101, 2000, 800, 6);

insert into emp values(3, '刘备备', 'MANAGER' ,'宋祖英', 20080808, 9000, 4000, 3);

insert into emp values(4, 'TOM', 'ENGINEER' ,'Steve', 20050612, 3000, 1000, 1);

insert into emp values(5, 'Steve', 'MANAGER' ,'宋祖英', 20110323, 80000, 9000, 1);

insert into emp values(6, '张飞飞', 'CLERK' ,'刘备备', 20101010, 2000, 1000, 3);

insert into emp values(7, 'SCOTT', 'CLERK' ,'刘备备', 20071204, 2000, 1000, 3);

insert into emp values(8, '宋祖英', 'Boss' ,'无', 20060603, 2000, 1000, 8);

insert into emp values(9, '曹仁人', 'SALESMAN' ,'曹操操', 20120130, 2000, 1000, 2);

insert into emp values(10, '曹操操', 'MANAGER' ,'宋祖英',20090815, 2000, 1000, 2);

insert into emp values(11, '酱油哥', 'HAPI' ,'毛泽东',20090215, 3, 1, 2);