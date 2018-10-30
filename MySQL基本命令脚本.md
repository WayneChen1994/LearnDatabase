#### ** 数据库简介

当您想收听最喜欢的歌曲时，可以从智能手机上打开播放列表。在这种情况下，播放列表是数据库就是从数据库中读取出来的。

当您拍摄照片并将其上传到微博，朋友圈等，这样的社交网络中的帐户时，您的照片库就有可能存储在一个数据库中。

数据库无处不在。 那么什么是数据库？ 

根据定义，数据库只是一个结构化的数据集合。

数据本质上相互关联，例如，产品属于产品类别并与多个标签相关联。这就是为什么要使用关系数据库。

在关系数据库中，我们使用表对产品，类别，标签等数据进行建模。 表包含列和行。它就像一个电子表格(Excel)。

表可以涉及的使用有：一对一，一对多，多对一关系等关系。

因为我们要处理大量的数据，所以需要一种方法来定义数据库，表等，并更有效地处理数据。 另外，我们可以将数据转换成数据信息。

> MySQL是一个数据库管理系统，也是一个关系数据库。它是由Oracle支持的开源软件。这意味着任何一个人都可以使用MySQL而不用支付一毛钱。 另外，如果需要，还可以更改其源代码或进行二次开发以满足您的需要。

#### 名词简介

**一.关系型数据库与非关系型数据库**

当前主流的关系型[数据库](http://lib.csdn.net/base/mysql)有[Oracle](http://lib.csdn.net/base/oracle)、DB2、Microsoft SQL Server、Microsoft Access、[MySQL](http://lib.csdn.net/base/mysql)等。

非关系型数据库有 **NoSql**、Cloudant，**mangodb**。

nosql和关系型数据库比较？
优点：
1）成本：nosql数据库简单易部署，基本都是开源软件，不需要像使用oracle那样花费大量成本购买使用，相比关系型数据库价格便宜。
2）查询速度：nosql数据库将数据存储于缓存之中，关系型数据库将数据存储在硬盘中，自然查询速度远不及nosql数据库。
3）存储数据的格式：nosql的存储格式是key,value形式、文档形式、图片形式等等，所以可以存储基础类型以及对象或者是集合等各种格式，而数据库则只支持基础类型。
4）扩展性：关系型数据库有类似join这样的多表查询机制的限制导致扩展很艰难。
缺点：
1）维护的工具和资料有限，因为nosql是属于新的技术，不能和关系型数据库10几年的技术同日而语。
2）不提供对sql的支持，如果不支持sql这样的工业标准，将产生一定用户的学习和使用成本。

3）不提供关系型数据库对事物的处理。

**非关系型数据库的优势：**1. 性能NOSQL是基于键值对的，可以想象成表中的主键和值的对应关系，而且不需要经过SQL层的解析，所以性能非常高。2. 可扩展性同样也是因为基于键值对，数据之间没有耦合性，所以非常容易水平扩展。

**关系型数据库的优势：**1. 复杂查询可以用SQL语句方便的在一个表以及多个表之间做非常复杂的数据查询。2. 事务支持使得对于安全性能很高的数据访问要求得以实现。对于这两类数据库，对方的优势就是自己的弱势，反之亦然。

**二、什么是主键、外键：**

关系型[数据库](http://lib.csdn.net/base/mysql)中的一条记录中有若干个属性，若其中某一个属性组(注意是组)能唯一标识一条记录，该属性组就可以成为一个主键 
比如  

学生表(学号，姓名，性别，班级) 
其中每个学生的学号是唯一的，学号就是一个主键 
课程表(课程编号,课程名,学分) 
其中课程编号是唯一的,课程编号就是一个主键 
成绩表(学号,课程号,成绩) 
成绩表中单一一个属性无法唯一标识一条记录，学号和课程号的组合才可以唯一标识一条记录，所以 学号和课程号的属性组是一个主键 

成绩表中的学号不是成绩表的主键，但它和学生表中的学号相对应，并且学生表中的学号是学生表的主键，则称成绩表中的学号是学生表的外键 

同理 成绩表中的课程号是课程表的外键 

**定义主键和外键主要是为了维护关系数据库的完整性，总结一下：**
1.**主键是能确定一条记录的唯一标识**，比如，一条记录包括身份正号，姓名，年龄。

身份证号是唯一能确定你这个人的，其他都可能有重复，所以，身份证号是主键。 
2.**外键用于与另一张表的关联**。是能确定另一张表记录的字段，用于保持数据的一致性。

比如，A表中的一个字段，是B表的主键，那他就可以是A表的外键。

#### mysql表示字段类型

> 正确地定义的表中的字段在数据库的整体优化是非常重要的。我们应该只使用真正需要使用类型和字段的大小; 如果知道只使用2个字符，就不使用10个字符宽定义一个字段。这些类型的字段(或列)，也被称为数据类型，数据存储这些字段之中。

MySQL使用许多不同的数据类型，总体上分为三类：数字，日期时间和字符串类型，布尔类型【bit】。

##### 1数字数据类型

- INT - 正常大小的整数，可以带符号。如果是有符号的，它允许的范围是从-2147483648到2147483647。如果是无符号，允许的范围是从0到4294967295。 可以指定多达**11位**的宽度。2^11 

- TINYINT - 一个非常小的整数，可以带符号。如果是有符号，它允许的范围是从-128到127。如果是无符号，允许的范围是从0到255，可以指定多达**4位**数的宽度。

- SMALLINT - 一个小的整数，可以带符号。如果有符号，允许范围为-32768至32767。如果无符号，允许的范围是从0到65535，可以指定最多**5位**的宽度。

- MEDIUMINT - 一个中等大小的整数，可以带符号。如果有符号，允许范围为-8388608至8388607。 如果无符号，允许的范围是从0到16777215，可以指定最多**9位**的宽度。

- BIGINT - 一个大的整数，可以带符号。如果有符号，允许范围为-9223372036854775808到9223372036854775807。如果无符号，允许的范围是从0到18446744073709551615. 可以指定最多**20位**的宽度。

- FLOAT(M,D) - 不能使用无符号的浮点数字。可以定义显示长度(M)和小数位数(D)。这不是必需的，并且默认为**10,2。**其中2是小数的位数，10是数字(包括小数)的总数。小数精度可以到**24个**浮点。

- DOUBLE(M,D) - 不能使用无符号的双精度浮点数。可以定义显示长度(M)和小数位数(D)。 这不是必需的，默认为**16,4，**其中4是小数的位数。小数精度可以达到**53位**的DOUBLE。 REAL是DOUBLE同义词。

- DECIMAL(M,D) - 非压缩浮点数不能是无符号的。在解包小数，每个小数对应于一个字节。定义显示长度(M)和小数(D)的数量是必需的。 NUMERIC是DECIMAL的同义词。

##### 2 日期和时间类型

MySQL的日期和时间数据类型包括：

- DATE - 以**YYYY-MM-DD**格式的日期，在1000-01-01和9999-12-31之间。 例如，1973年12月30日将被存储为1973-12-30。
- DATETIME - 日期和时间组合以**YYYY-MM-DD HH:MM:SS**格式，在1000-01-01 00:00:00 到9999-12-31 23:59:59之间。例如，1973年12月30日下午3:30，会被存储为1973-12-30 15:30:00。
- TIMESTAMP - 1970年1月1日午夜之间的**时间戳**，到2037的某个时候。这看起来像前面的DATETIME格式，无需只是数字之间的连字符; 1973年12月30日下午3点30分将被存储为19731230153000(YYYYMMDDHHMMSS)。
- TIME - 存储时间在**HH:MM:SS**格式。
- YEAR(M) - 以2位或4位数字格式来存储年份。如果长度指定为2(例如YEAR(2))，年份就可以为1970至2069(70〜69)。如果长度指定为4，年份范围是1901-2155，默认长度为4。

##### 3字符串类型

虽然数字和日期类型比较有意思，但存储大多数数据都可能是字符串格式。 下面列出了在MySQL中常见的字符串数据类型。

- CHAR(M) - **固定长度**的字符串是以长度为1到255之间个字符长度(例如：CHAR(5))，存储右空格填充到指定的长度。 限定长度不是必需的，它会默认为1。
- VARCHAR(M) - **可变长度的字符串**是以长度为1到255之间字符数(高版本的MySQL超过255); 例如： VARCHAR(25). **创建VARCHAR类型字段时，必须定义长度**。
- BLOB or TEXT - 字段的最大长度是65535个字符。 BLOB是“二进制大对象”，并用来存储大的二进制数据，如图像或其他类型的文件。定义为TEXT文本字段还持有大量的数据; 两者之间的区别是，排序和比较上存储的数据，BLOB大小写敏感，而TEXT字段不区分大小写。不用指定BLOB或TEXT的长度。
- TINYBLOB 或 TINYTEXT - BLOB或TEXT列用255个字符的最大长度。不指定TINYBLOB或TINYTEXT的长度。
- MEDIUMBLOB or MEDIUMTEXT - BLOB或TEXT列具有16777215字符的最大长度。不指定MEDIUMBLOB或MEDIUMTEXT的长度。
- LONGBLOB 或 LONGTEXT -  BLOB或TEXT列具有4294967295字符的最大长度。不指定LONGBLOB或LONGTEXT的长度。
- **ENUM - 枚举**是一个奇特的术语列表。当定义一个ENUM，要创建它的值的列表，这些是必须用于选择的项(也可以是NULL)。例如，如果想要字段包含“A”或“B”或“C”，那么可以定义为ENUM为 ENUM(“A”，“B”，“C”)也只有这些值(或NULL)才能用来填充这个字段。

####一、基本命令

#####1、启动服务

    说明：以管理员身份运行cmd
    格式：net start 服务名称
    示例：net start mysql57

#####2、停止服务

    说明：以管理员身份运行cmd
    格式：net stop 服务名称
    示例：net stop mysql57

#####3、连接数据

    格式：mysql -u 用户名 -p
    示例：mysql -u root -p
    输入密码(安装时设置的)

#####4、退出登录(断开连接)

​    quit或exit

#####5、查看版本（连接后可以执行）

​    示例：select version();

#####6、显示当前时间（连接后可以执行）

​    示例：select now();

#####7、远程连接

    格式：mysql -h ip地址  -u 用户名   -p
    输入对方mysql密码

####二、数据库操作

#####1、创建数据库

```mysql
#格式：
create database 数据库名 charset=utf8;
#示例：
create database testdb charset=utf8;
```

   ##### 2、删除数据库
```mysql
    #格式：
    drop database 数据库名;
    #示例：
    drop database testdb;
```

#####3、切换数据库
```mysql
#格式：
use 数据库名;
#示例：
use testdb;
```
#####4、查看当前选择的数据库
```mysql
select database();
```

##### 5、查看所有的数据库

```mysql
show databases；
```



####三、表操作

   #####1、查看当前数据库中所有表
```mysql
show tables;
```
  ##### 2、创建表
```mysql
    #格式：
    create table 表名(列及类型);
    #说明：
          auto_increment表示自增长   
          primary key表示主键  
          not null表示不为空
          bit 二进制，表示布尔类型
          default 默认值
          if not exists 若不存在
    #示例：
    create table if not exists student(id int auto_increment primary key, name varchar(20) not null, age smallint not null, gender bit default 1, address varchar(20), isDelete bit default 0)charset=utf8;
```
> 创建一个教师表，id，name，gender，age，profession

 #####  3、删除表

```mysql
    格式：drop table 表名;
    示例：drop table student;
```
  ##### 4、查看表结构
```mysql
    格式：desc 表名;
    示例：desc student;
```
   #####5、查看建表语句
        格式：show create table 表名;
        示例：show create table student;

#####6、重命名表名
    格式：rename table 原表名 to 新表名;
    示例：rename table car to newCar;
   #####7、修改表

```mysql
格式：alter table 表名 add|change|drop 列名 类型;
示例：alter table newcar add isDelete bit default 0
注意：删除的时候不用指定类型
```



####四、数据操作

#####1、增

   ######a、全列插入
```mysql
    格式：insert into 表名 values(...);
    说明：主键列是自动增长，但是在全列插入时需要占位，通常使用0，插入成功以后以实际数据为准
    示例：insert into student values(0,"tom",19,1,"北京",0);
```
   ######b、缺省插入
```mysql
    格式：insert into 表名(列1,列2,……) values(值1,值2,……);
    示例：insert into student(name,age,address) values("lilei",19,"上海");
```

######c、同时插入多条数据
```mysql
格式：insert into 表名 values(...),(...),……
示例：insert into student values(0,"hanmeimei",18,0,"北京",0),(0,"poi",22,1,"海南",0),(0,"wenli",20,0,"石家庄",0);
```
#####2、删

```mysql
   格式：delete from 表名 where 条件;  
   示例：delete from student where id=4;
   注意：没有条件是全部删除，慎用
```

伪删除

#####3、改

    格式：update  表名 set 列1=值1,列2=值2,…… where 条件;
    示例：update student set age=16 where id=7;  
    注意：没有条件是全部列都修改，慎用

#####4、查

    说明：查询表中的全部数据
    格式：select * from 表名;
    示例：select * from student;

####五、查

   #####1、基本语法
```mysql
    格式：select * from 表名;
    说明：
          a、from关键字后面是表名，表示数据来源于这张表
          b、select后面写表中的列名，如果是*表示在结果集中显示表中的所有列
          c、在select后面的列名部分，可以使用as为列起别名，这个别名显示在结果集中
          d、如果要查询多个列，之间使用逗号分隔
```

实例：

```mysql
 select * from student;
 select name, age from student;
 select name as a, age from student;
```

#####2、消除重复行

> 在select后面列前面使用distinct可以消除重复的行

    示例：

```mysql
select gender from student;
select distinct gender from student;
```

> 查看消除指定班级py-1803中年龄出现重复的。

##### 3、条件查询

a、语法
        select * from 表名 where 条件
    b、比较运算符
        等于        =
        大于        >
        小于        <
        大于等于    >=
        小于等于    <=
        不等于      !=或<>

> 需求：查询id值大于8的所有数据

```mysql
select * from student where id>8;
```

 c、逻辑运算符
        and    并且
        or     或者
        not    非

> 需求：查询id值大于7的女同学

```mysql
select * from student where id>7 and gender=0;
```

查询不是py1803的年龄大于18的男同学

d、模糊查询

like
        %表示任意多个任意字符
        _表示一个任意字符

> 需求：查询姓习的同学

```mysql
 insert into student values(0,"习近平",65,1,"北京",0);
 insert into student values(0,"习大",66,1,"北京",0);
 
 select * from student where name like "习%";
 select * from student where name like "习_";      
```

> 查询名字以蛋结尾的，并且不是男生，年龄大于18的学生的名字与年龄，班级。



e、范围查询

in                表示在一个非连续的范围内
 between...and...  表示在一个连续的范围内

> 需求：查询编号为8、10、12的学生

```mysql
select * from student where id in (8,10,12);
```

> 需求：查询编号为6到8的学生

```mysql
select * from student where id between 6 and 8;
```

> 查询年龄在18~20之间不是女生的学生的姓名，年龄以及班级。



 f、空判断

 注意：null与""是不同
  判断空：is null
  判断非空： is not null

> 需求：查询没有地址的同学

```mysql
insert into student(name,age) values("特朗普",70);

select * from student where address is null;
```

> 需求：查询有地址的同学

```mysql
select * from student where address is not null;
```

> 查询专业不为空的所有的女老师



g、优先级
        小括号，not，比较运算符，逻辑运算符
        and比or优先级高，如果同时出现并希望先选or,需要结合()来使用

> 需求：求名字以li结尾的或者年龄为18且地址为空的同学

```mysql
select * from student where address is null and (name like "%li" or age = 18);
```

> 名字包含‘小’的，年龄在18~20之间的男学生



##### 4、聚合

为了快速得到统计数据，提供了5个聚合函数
    a、count(*)    表示计算总行数，括号中可以写*和列名
    b、max(列)     表示求此列的最大值
    c、min(列)     表示求此列的最小值
    d、sum(列)     表示求此列的和
    e、avg(列)     表示求此列的平均值

> 需求：查询学生总数

```mysql
select count(*) from student;
```

> 需求：查询女生的编号最大值

```mysql
select max(id) from student where gender=0;
```

> 查询女生的编号最小值

```mysql
select min(id) from student where gender=0;
```

> 查询所有学生的年龄和

```mysql
select sum(age) from student;
```

> 查询所有学生的年龄平均值

```mysql
select avg(age) from student;
```

》1.查询男生的最高分，女生最高分，男生平均分，女生平均分



》创建一个最美应用，用户注册表，注册的时候字段，插入数据

1.username  2.password  3.phonenum

=》模仿用户登陆时，后台操作，查询



##### 5、分组

    按照字段分组，表示此字段相同的数据会被放到一个集合中.分组后，只能查询出相同的数据列，对于有差异的数据列无法显示在结果集中,可以对分组后的数据进行统计，做聚合运算.

```mysql
#语法
select 列1,列2,聚合…… from 表名 group by 列1,列2,列3,……;
```

> 需求：查询男女生总数

```mysql
select gender,count(*) from student group by gender;
select name,gender,count(*) from student group by gender,age;
```

 分组后的数据筛选：

 where与having的区别：
 1、where是对from后面指定的表进行筛选，属于对原始数据的筛选
 2、having是对group by的结果集进行筛选

```mysql
#语法
select 列1,列2,聚合…… from 表名 group by 列1,列2,列3,…… having 列1,……聚合……;
```

实例：

```mysql
select gender,count(*) from student group by gender having gender;
```

查询每个班级中不同年龄学生总数



#####6、排序

```mysql
#语法：
select * from 表名 order by 列1 asc|desc，列2 asc|desc , ……;
```

    说明：
        a、将数据按照列1进行排序，如果某些列1的值相同，则按照列2进行排序
        b、默认按照从小到大的顺序排序
        c、asc升序
        d、desc降序

> 需求：将没有被删除的数据按年龄排序

```mysql
select * from student where isDelete=0 order by age desc;
select * from student where isDelete=0 order by age desc, id desc;
```

##### 7、分页

```mysql
#语法：
select * from 表名 limit start,count;
```

 说明：start索引从0开始

例如：

```mysql
 select * from student limit 0,3;
 select * from student limit 3,3;
 select * from student where gender=1 limit 0,3;
```

####六、关联

一、定义主键和外键主要是为了维护关系数据库的完整性 

1.主键是能确定一条记录的唯一标识，比如，一条记录包括身份正号，姓名，年龄。 

2.外键用于与另一张表的关联。是能确定另一张表记录的字段，用于保持数据的一致性。

 二、  主键、外键和索引的区别 

主键、外键和索引的区别？

|        | 主键                                       | 外键                                                 | 索引                               |
| ------ | ------------------------------------------ | ---------------------------------------------------- | ---------------------------------- |
| 定义： | 唯一标识一条记录，不能有重复的，不允许为空 | 表的外键是另一表的主键, 外键可以有重复的, 可以是空值 | 该字段没有重复值，但可以有一个空值 |
| 作用： | 用来保证数据完整性                         | 用来和其他表建立联系用的                             | 是提高查询排序的速度               |
| 个数： | 主键只能有一个                             | 一个表可以有多个外键                                 | 一个表可以有多个惟一索引           |

 

建表语句：

```mysql
mysql>create table class(id int auto_increment primary key, name varchar(20) not null, stuNum int not null);

mysql>create table students(id int auto_increment primary key, name varchar(20) not null, gender bit default 1, classid int not null, foreign key(classid) references class(id));

```


```mysql
#插入一些数据：
insert into class values(0, "python01", 55),(0, "python02", 50),(0, "python03", 60),(0, "python04", 80);

insert into students values(0, "tom", 1, 1);
insert into students values(0, "lilei", 1, 10);
insert into students values(0, "jack", 1, 2);
```


```mysql
select * from students;
关联查询：
select students.name,class.name from class inner join students on class.id=students.classid;

select students.name,class.name from class left join students on class.id=students.classid;

select students.name,class.name from class right join students on class.id=students.classid;
```


```mysql
分类：
1、表A inner join 表B：
    表A与表B匹配的行会出现在结果集中
2、表A left join 表B：
    表A与表B匹配的行会出现在结果集中，外加表A中独有的数据，未对应的数据使用null填充
3、表A right join 表B：
    表A与表B匹配的行会出现在结果集中，外加表B中独有的数据，未对应的数据使用null填充
```


#### 七、MySQL事务

> 事务是数据库处理操作，其中执行就好像它是一个单一的一组有序的工作单元。换言之，事务将永远不会是完全的，除非在组内每个单独的操作是成功的。如果事务中的任何操作失败，整个事务将失败。

##### 事务性质

事务具有以下四个标准属性，通常由首字母缩写ACID简称：

- 原子性: 确保了工作单位中的所有操作都成功完成; 否则，事务被中止，在失败时会被回滚到事务操作以前的状态。
- 一致性：可确保数据库在正确的更改状态在一个成功提交事务。
- 隔离: 使事务相互独立地操作。
- 持久性: 确保了提交事务的结果或系统故障情况下仍然存在作用。

在MySQL中，事务以BEGIN WORK语句开始开始工作，并使用COMMIT或ROLLBACK语句结束。SQL命令在开始和结束语句之间构成大量事务。

#####提交和回滚

这两个关键字Commit和Rollback主要用于MySQL的事务。

- 当一个成功的事务完成后，COMMIT命令发出的变化对所有涉及的表将生效。
- 如果发生故障，ROLLBACK命令发出后，事务中引用的每个表将恢复到事务开始之前的状态。

#####【拓展】在MySQL的事务安全表类型

不能直接使用事务，可以使用但它们没有安全保障。如果打算使用事务在MySQL编程，那么需要使用一个特殊的方式来创建表。 有许多类型的表其支持事务，但目前最流行的一种是：InnoDB.

支持InnoDB表需要特定的编译参数，在源代码编译MySQL时。如果MySQL版本不支持InnoDB，得要求互联网服务提供商建立一个版本的MySQL的InnoDB表类型的支持，或 下载并安装MySQL-Max二进制分发的Windows版本，或者Linux/UNIX开发环境中工作的表类型。

如果你的MySQL安装支持InnoDB表，简直就是一个TYPE= InnoDB的定义添加到表创建语句后面。 链接了解更多有关: [InnoDB](http://www.mysql.com/doc/I/n/InnoDB.html)

例如：

```mysql
create table tcount_tbl( tutorial_author varchar(40) NOT NULL,tutorial_count  INT) TYPE=InnoDB;
```

可以使用其它类型的表 GEMINI 或 BDB, 但它取决于安装MySQL时，是否支持这两种类型。

 

#### 八、Mysql 与python

> Python具有内置的SQLite支持。 在本节中，我们将学习使用MySQL的相关概念和知识。 在早期Python版本一般都使用MySQLdb模块，但这个MySQL的流行接口与*Python 3*不兼容。因此，在教程中将使用[PyMySQL模块](http://github.com/PyMySQL/PyMySQL/)

##### 1.什么是PyMySQL？

> PyMySQL是从Python连接到MySQL数据库服务器的接口。 它实现了Python数据库API v2.0，并包含一个纯Python的MySQL客户端库

##### 2.安装PyMySQL

```python
pip3 install PyMySQL
```

##### 3.数据库连接

在连接到MySQL数据库之前，请确保以下几点：

- 已经创建了一个数据库：`testdb`。
- 已经在`testdb`中创建了一个表:`student`。
- `student`表格包含:`id`，`name`，`age`，`sex`字段。
- MySQL用户“root”和密码“root”可以访问：`testdb`。
- Python模块PyMySQL已正确安装在您的计算机上。
- 已经通过[MySQL教程](http://www.yiibai.com/mysql)了解MySQL基础知识。

创建表

```mysql
CREATE TABLE student (
  id int(10) NOT NULL AUTO_INCREMENT,
  name char(20) NOT NULL,
  age int(11) DEFAULT NULL,
  sex char(1) DEFAULT NULL,
  score float DEFAULT NULL,
  PRIMARY KEY (id)
) ENGINE=InnoDB DEFAULT CHARSET=utf8;
```

##### 4.连接pymsql

```python
#!/usr/bin/python3
#coding=utf-8

#导入包
import pymysql

# 打开数据库连接
db = pymysql.connect("localhost","root","root","testdb" )

# 使用cursor()方法获取一个游标
cursor = db.cursor()

# 执行sql语句中查询版本信息的方法
cursor.execute("SELECT VERSION()")

# 使用 fetchone() 方法获取一条数据
data = cursor.fetchone()

#打印版本信息
print ("Database version : %s " % data)

# 关闭连接
db.close()
```

##### 5.创建数据库表

```python
#!/usr/bin/python3
#coding=utf-8

import pymysql

# 打开数据库连接
db = pymysql.connect("localhost","root","root","testdb" )

# 准备一个游标
cursor = db.cursor()

# 若表存在则删除
cursor.execute("DROP TABLE IF EXISTS student")

# 准备建表的语句
sql = """CREATE TABLE student (
  id int(10) NOT NULL AUTO_INCREMENT,
  name char(20) NOT NULL,
  age int(11) DEFAULT NULL,
  sex char(1) DEFAULT NULL,
  score float DEFAULT NULL,
  PRIMARY KEY (id)
) ENGINE=InnoDB DEFAULT CHARSET=utf8;;"""
#执行sql语句
cursor.execute(sql)
print("Created table Successfull.")
# 断开连接
db.close()
```

 ##### 6.插入操作

当要将记录创建到数据库表中时，需要执行`INSERT`操作。

以下示例执行SQL的insert语句以在student表中创建一条(多条)记录

```mysql
#!/usr/bin/python3
#coding=utf-8

import pymysql

db = pymysql.connect("localhost","root","root","testdb" )

cursor = db.cursor()

# 准备sql语句
sql = """INSERT INTO student(name,
   age, sex, score)
   VALUES ('Mac', 18, 0,90)"""
try:
   # 执行sql语句
   cursor.execute(sql)
   # 提交事务
   db.commit()
except:
   # 若出现错误，则回滚
   db.rollback()

db.close()
```

动态创建SQL查询

```python
#!/usr/bin/python3
#coding=utf-8

import pymysql

# Open database connection
db = pymysql.connect("localhost","root","123456","test" )

# prepare a cursor object using cursor() method
cursor = db.cursor()

# Prepare SQL query to INSERT a record into the database.
sql = "INSERT INTO EMPLOYEE(name, age, sex, scroe) VALUES ('%s', '%d', '%c', '%f')" % ('Max', 25, 0, 89)
try:
   # 执行sql语句
   cursor.execute(sql)
   # 提交事务
   db.commit()
except:
   # 回滚
   db.rollback()
db.close()
```

##### 7.读取操作

任何数据库上的读操作表示要从数据库中读取获取一些有用的信息。

在建立数据库连接后，就可以对此数据库进行查询了。 可以使用`fetchone()`方法获取单条记录或`fetchall()`方法从数据库表中获取多个值。

- `fetchone()` - 它获取查询结果集的下一行。 结果集是当使用游标对象来查询表时返回的对象。
- `fetchall()` - 它获取结果集中的所有行。 如果已经从结果集中提取了一些行，则从结果集中检索剩余的行。
- `rowcount` - 这是一个只读属性，并返回受`execute()`方法影响的行数。

```python
#!/usr/bin/python3
#coding=utf-8

import pymysql


db = pymysql.connect("localhost","root","root","testdb" )

cursor = db.cursor()
# 按字典返回 
# cursor = db.cursor(pymysql.cursors.DictCursor)

sql = "SELECT * FROM student WHERE age > %d" % (20)
#print (sql)
try:
   cursor.execute(sql)
   #获取查找到的所有行数
   results = cursor.fetchall()
	#遍历结果集
   for row in results:
      #print (row)
      name = row[1]
      age = row[2]
      sex = row[3]
      score = row[4]
      print ("name = %s,age = %s,sex = %c,score = %f" %(name, age, sex, score))
except:
   import traceback
   #打印异常
   traceback.print_exc()

db.close()
```

##### 8.更新操作

PDATE语句可对任何数据库中的数据进行更新操作，它可用于更新数据库中已有的一个或多个记录。

以下程序将所有`SEX`字段的值为“`0`”的记录的年龄(`age`字段)更新为增加一年。

```python
#!/usr/bin/python3
#coding=utf-8

import pymysql

db = pymysql.connect("localhost","root","root","testdb" )

cursor = db.cursor()

sql = "UPDATE student SET AGE = AGE + 1 WHERE SEX = '%c'" % ('0')
try:
   cursor.execute(sql)
   db.commit()
except:
 
   db.rollback()
db.close()
```

##### 9.删除操作

当要从数据库中删除一些记录时，那么可以执行`DELETE`操作。 以下是删除student中`AGE`超过`40`的所有记录的程序 。

```python
#!/usr/bin/python3
#coding=utf-8

import pymysql

db = pymysql.connect("localhost","root","root","testdb" )

cursor = db.cursor()

sql = "DELETE FROM student WHERE AGE > '%d'" % (40)
try:
   cursor.execute(sql)
   db.commit()
except:
  
   db.rollback()

db.close()
```

#### 九、工具类【封装mysql】

```python
import pymysql

class DBHelper():
    def __init__(self,host, user, passwd, dbName):
        self.host = host
        self.user = user
        self.passwd = passwd
        self.dbName = dbName
    def connet(self):
        self.db = pymysql.connect(self.host,self.user,self.passwd,self.dbName)
        self.cursor = self.db.cursor()
        
    def close(self):
        self.cursor.close()
        self.db.close()

    def get_one(self, sql):
        res = None
        try:
            self.connet()
            self.cursor.execute(sql)
            res = self.cursor.fetchone()
            self.close()
        except:
            print("查询失败")
        return res
    
    
    def get_all(self, sql):
        res = ()
        try:
            self.connet()
            self.cursor.execute(sql)
            res = self.cursor.fetchall()
            self.close()
        except:
            print("查询失败")
        return res



    def insert(self, sql):
        return self.__edit(sql)
    
    def update(self, sql):
        return self.__edit(sql)
    
    
    def delete(self, sql):
        return self.__edit(sql)

    def __edit(self,sql):
        count = 0
        try:
            self.connet()
            count = self.cursor.execute(sql)
            self.db.commit()
            self.close()
        except:
            print("事物提交失败")
            self.db.rollback()
        return count
```

#### 拓展

mysql的索引类型：

普通索引：最基本的索引，没有任何限制

唯一索引：使用唯一索引的时候，此行数据中不准有重复的值，针对这一列数据都要求是唯一的。

主键索引：它是一种特殊的索引，不允许有空值，一般是在建表的时候同时创建主键索引，常用于用户id。

全文索引：对于全局搜索的数据进行全文索引。

一、创建索引：

1.普通索引

基本语法： alter table 表名  add  index(字段)

示例：alter table student  add index(username);

解释：为student表的username字段增加索引。

2.唯一索引

基本语法：alter table  表  add  unique(字段)；

示例：alter table student add  unique(email);

示例解释：为student表的email字段增加唯一索引。

3.全文索引

基本语法： alter table 表 add fulltext(字段)；

示例：alter table  student fulltext(content);

示例解释：为student表的content字段增加唯一索引

4.主键索引

基本语法：alter table add primary key(字段)；

示例：alter table student add primary key(id);

示例解释：为student表的id字段增加主键索引。

二、删除索引：

alter table  表 drop index 索引名；

