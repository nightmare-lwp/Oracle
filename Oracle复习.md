# Oracle复习

本次考试主要包括五种题型：
1、单选题 ，分析select语句执行后的查询结果
2、判断题，针对小算法的实现进行代码补全
3、方案对象，表的创建DDL，以及测试数据维护DML
4、查询设计，常用的查询设计，复杂语法可以参考单选题
5、PLSQL程序设计，触发器、函数、过程，能力差的同学要尽量把子程序基本语法结构给出来。其他知识点包括if分支、for循环、游标、异常等

查询设计是按查询结果字段，查询条件给分，不能写全对也要把结构给出来。复杂查询前面选择题有语法参考。小算法也主要考双循环

## 1.单选题

### SELECT基础语法

![image-20230213161050577](Oracle复习.assets/image-20230213161050577.png)

[]表示可选，{}表示必填

select  [distinct 去重]  {*所有字段，column列名 [alias别名]，...}

from table表名

[where condition(s)条件]

[order by {column列名，expr表达式，alias别名} [asc升序|desc降序]]

#### 定义列的别名

![image-20230213162624882](Oracle复习.assets/image-20230213162624882.png)

定义别名时，用“”双引号。

#### 连接符||

![image-20230213162813119](Oracle复习.assets/image-20230213162813119.png)

用连接符连接字符串时用‘’单引号。

#### 条件（WHERE）:比较符

![image-20230213162938266](Oracle复习.assets/image-20230213162938266.png)

不等于的符号千奇百怪。还是!=亲切

![image-20230213163026209](Oracle复习.assets/image-20230213163026209.png)

##### 比较符LIKE

![image-20230213163117565](Oracle复习.assets/image-20230213163117565.png)

定义：escape关键字经常用于使某些特殊字符，如通配符：’%’,’_‘转义为它们原来的字符的意义，被定义的转义字符通常使用’\‘,但是也可以使用其他的符号。

![image-20230213163459868](Oracle复习.assets/image-20230213163459868.png)

#### 条件（WHERE）:逻辑操作符

![image-20230213163550754](Oracle复习.assets/image-20230213163550754.png)

#### 条件（WHERE）:  优先规则

![image-20230213163645350](Oracle复习.assets/image-20230213163645350.png)

可能存在陷阱（感觉必考）：若没括号，and的优先级高于or，即and的两个语句先结合，如上图。

#### 排序（ORDER BY子句）

![image-20230213163851736](Oracle复习.assets/image-20230213163851736.png)

### SELECT进阶单行函数

#### 字符函数

##### 字符函数:分类

![image-20230213164549439](Oracle复习.assets/image-20230213164549439.png)

##### 字符函数:常用函数列表

![image-20230213164636989](Oracle复习.assets/image-20230213164636989.png)

##### 字符函数：用例

![image-20230213164746246](Oracle复习.assets/image-20230213164746246.png)

#### 数值函数

##### 数值函数:常用函数列表

![image-20230213165001152](Oracle复习.assets/image-20230213165001152.png)

##### 数值函数： ROUND函数（四舍五入）

![image-20230213165224305](Oracle复习.assets/image-20230213165224305.png)

##### 数值函数： TRUNC函数（截取）

![image-20230213165535872](Oracle复习.assets/image-20230213165535872.png)

##### 数值函数： MOD函数（取模）

![image-20230213165556088](Oracle复习.assets/image-20230213165556088.png)

#### 日期函数

##### 日期类型

![image-20230213170138032](Oracle复习.assets/image-20230213170138032.png)

##### 日期运算

![image-20230213170221644](Oracle复习.assets/image-20230213170221644.png)

##### 日期函数

![image-20230213182501306](Oracle复习.assets/image-20230213182501306.png)

#### 转换函数

##### 隐式转换-赋值

![image-20230213185153408](Oracle复习.assets/image-20230213185153408.png)

##### 隐式转换-表达式运算

![image-20230213185309524](Oracle复习.assets/image-20230213185309524.png)

##### 函数TO_CHAR (日期)

![image-20230213185554136](Oracle复习.assets/image-20230213185554136.png)

![image-20230213190413925](Oracle复习.assets/image-20230213190413925.png)

##### 函数TO_CHAR (数值)

![image-20230213190749857](Oracle复习.assets/image-20230213190749857.png)

![image-20230213190812241](Oracle复习.assets/image-20230213190812241.png)

##### 函数TO_NUMBER TO_DATE

![image-20230213191000410](Oracle复习.assets/image-20230213191000410.png)

##### 空值置换函数

![image-20230213191149620](Oracle复习.assets/image-20230213191149620.png)

![image-20230213191255832](Oracle复习.assets/image-20230213191255832.png)

![image-20230213191320014](Oracle复习.assets/image-20230213191320014.png)

#### 条件表达式

##### 条件表达式： CASE表达式

![image-20230213191610873](Oracle复习.assets/image-20230213191610873.png)

##### 条件表达式： DECODE函数

![image-20230213191659885](Oracle复习.assets/image-20230213191659885.png)

### SELECT进阶高级查询

#### 连接查询

![image-20230213192627500](Oracle复习.assets/image-20230213192627500.png)

##### 外连接

![image-20230213193005478](Oracle复习.assets/image-20230213193005478.png)

![image-20230213193026430](Oracle复习.assets/image-20230213193026430.png)

![image-20230213193219969](Oracle复习.assets/image-20230213193219969.png)

##### 递归查询（树查询）

![image-20230213193413963](Oracle复习.assets/image-20230213193413963.png)

![image-20230213194113252](Oracle复习.assets/image-20230213194113252.png)

##### 集合操作符

![image-20230213194210215](Oracle复习.assets/image-20230213194210215.png)

##### 分组函数

![image-20230213194532118](Oracle复习.assets/image-20230213194532118.png)

![image-20230213194603927](Oracle复习.assets/image-20230213194603927.png)

![image-20230213194638305](Oracle复习.assets/image-20230213194638305.png)

##### 限制选择组

![image-20230213194731787](Oracle复习.assets/image-20230213194731787.png)

![image-20230213194809605](Oracle复习.assets/image-20230213194809605.png)

##### 非法使用分组函数

![image-20230213195127775](Oracle复习.assets/image-20230213195127775.png)

select count（ename） from emp 不会报错，多个字段就会报错。

![image-20230213195233429](Oracle复习.assets/image-20230213195233429.png)

##### 单行子查询

![image-20230213195436190](Oracle复习.assets/image-20230213195436190.png)

##### 多行子查询

![image-20230213195453174](Oracle复习.assets/image-20230213195453174.png)

## 2.判断题

双循坏小算法

![image-20230213205246918](Oracle复习.assets/image-20230213205246918.png)

dbms_output.put()        不换行不输出

dbms_output.put_line() 输出加换行

dbms_output.new_line  换行并把缓存里的输出，本身不能输出东西

![QQ截图20230213205949](Oracle复习.assets/QQ截图20230213205949.png)

## 3.方案对象，DDL，DML

### 方案对象

![image-20230213211509950](Oracle复习.assets/image-20230213211509950.png)

![image-20230213211908027](Oracle复习.assets/image-20230213211908027.png)

![image-20230213211929521](Oracle复习.assets/image-20230213211929521.png)



考不到那么难

### DDL

![image-20230213212349873](Oracle复习.assets/image-20230213212349873.png)

#### 建表

![image-20230213212818521](Oracle复习.assets/image-20230213212818521.png)

#### 使用子查询建表

![image-20230213212852698](Oracle复习.assets/image-20230213212852698.png)

#### 更改表

![image-20230213213006717](Oracle复习.assets/image-20230213213006717.png)

#### 删除表

![image-20230213213207850](Oracle复习.assets/image-20230213213207850.png)

#### 改变表名称

![image-20230213213247464](Oracle复习.assets/image-20230213213247464.png)

#### 截断表

truncate

![image-20230213213338127](Oracle复习.assets/image-20230213213338127.png)

#### 增加注释

![image-20230213213416425](Oracle复习.assets/image-20230213213416425.png)

#### 创建和管理约束

![image-20230213213536633](Oracle复习.assets/image-20230213213536633.png)

##### 定义约束

![image-20230213213625978](Oracle复习.assets/image-20230213213625978.png)

两种约束：列约束和表约束

constraint

![image-20230213213718544](Oracle复习.assets/image-20230213213718544.png)

##### 非空约束

![image-20230213214001243](Oracle复习.assets/image-20230213214001243.png)

##### 唯一码约束

![image-20230213214027883](Oracle复习.assets/image-20230213214027883.png)

##### 主键约束

![image-20230213214101420](Oracle复习.assets/image-20230213214101420.png)

##### 外键约束

![image-20230213214557667](Oracle复习.assets/image-20230213214557667.png)

##### CHECK约束

![image-20230213215118917](Oracle复习.assets/image-20230213215118917.png)

##### 增加约束

![image-20230213215313097](Oracle复习.assets/image-20230213215313097.png)

##### 删除约束

![image-20230213215408289](Oracle复习.assets/image-20230213215408289.png)

##### 禁用约束

![image-20230213215454327](Oracle复习.assets/image-20230213215454327.png)

### 视图

#### 视图

![image-20230214135515334](Oracle复习.assets/image-20230214135515334.png)

![image-20230214135541010](Oracle复习.assets/image-20230214135541010.png)

#### 序列

![image-20230214135921331](Oracle复习.assets/image-20230214135921331.png)

![image-20230214140034274](Oracle复习.assets/image-20230214140034274.png)

#### 索引

![image-20230214140118281](Oracle复习.assets/image-20230214140118281.png)

#### 同义词

![image-20230214140221345](Oracle复习.assets/image-20230214140221345.png)

## 4.查询设计

见单选题

## 5.PLSQL程序设计

### 数据类型和变量

#### PL/SQL块结构

![image-20230213201223986](Oracle复习.assets/image-20230213201223986.png)

![image-20230213201244998](Oracle复习.assets/image-20230213201244998.png)

#### PL/SQL块块种类

![image-20230213201326478](Oracle复习.assets/image-20230213201326478.png)

#### 声明PL/SQL变量

![image-20230213201512645](Oracle复习.assets/image-20230213201512645.png)

![image-20230213201638827](Oracle复习.assets/image-20230213201638827.png)

#### 标量变量声明

![image-20230213201907347](Oracle复习.assets/image-20230213201907347.png)

#### 引用类型

![image-20230213201943505](Oracle复习.assets/image-20230213201943505.png)

![image-20230213202030278](Oracle复习.assets/image-20230213202030278.png)

![image-20230213202043784](Oracle复习.assets/image-20230213202043784.png)

### SQL的使用

#### select要用into

![image-20230213202537369](Oracle复习.assets/image-20230213202537369.png)

#### 使用&输入

![image-20230213202555155](Oracle复习.assets/image-20230213202555155.png)

### 控制语句

#### 分支结构

![image-20230213203314227](Oracle复习.assets/image-20230213203314227.png)

![image-20230213203858081](Oracle复习.assets/image-20230213203858081.png)

case结构

![image-20230213204117132](Oracle复习.assets/image-20230213204117132.png)

#### 循环控制结构

##### Basic Loop

![image-20230213204312022](Oracle复习.assets/image-20230213204312022.png)

![image-20230213204338476](Oracle复习.assets/image-20230213204338476.png)

##### FOR Loop

![image-20230213204407547](Oracle复习.assets/image-20230213204407547.png)

![image-20230213204436483](Oracle复习.assets/image-20230213204436483.png)

##### WHILE Loop

![image-20230213204530032](Oracle复习.assets/image-20230213204530032.png)

![image-20230213204541612](Oracle复习.assets/image-20230213204541612.png)

### 游标Cursors

#### 隐式游标

![image-20230213220353533](Oracle复习.assets/image-20230213220353533.png)

![image-20230213220415913](Oracle复习.assets/image-20230213220415913.png)

应该用不上

#### 显式游标

![image-20230213220542776](Oracle复习.assets/image-20230213220542776.png)

##### 处理流程

![image-20230213220602362](Oracle复习.assets/image-20230213220602362.png)

##### 声明游标

![image-20230213220654299](Oracle复习.assets/image-20230213220654299.png)

![image-20230213220721206](Oracle复习.assets/image-20230213220721206.png)

##### 打开游标

![image-20230213220750645](Oracle复习.assets/image-20230213220750645.png)

##### 从游标中提取数据

![image-20230213220811365](Oracle复习.assets/image-20230213220811365.png)

##### 关闭游标

![image-20230213221012350](Oracle复习.assets/image-20230213221012350.png)

##### 显示游标的属性

![image-20230213221031744](Oracle复习.assets/image-20230213221031744.png)

##### 游标提取控制

![image-20230213221636467](Oracle复习.assets/image-20230213221636467.png)

###### 游标提取BASIC LOOP

![image-20230214135134132](Oracle复习.assets/image-20230214135134132.png)

###### 游标提取WHILE LOOP

![image-20230214135153177](Oracle复习.assets/image-20230214135153177.png)

###### 游标提取FOR LOOP

![image-20230213221708096](Oracle复习.assets/image-20230213221708096.png)

![image-20230213221731778](Oracle复习.assets/image-20230213221731778.png)

![image-20230213221744983](Oracle复习.assets/image-20230213221744983.png)

高级

##### 带参数的游标

![image-20230213221811390](Oracle复习.assets/image-20230213221811390.png)

更高级，没用过

### 异常Exception

#### 异常处理语法

![image-20230213221952251](Oracle复习.assets/image-20230213221952251.png)

#### 捕获异常规则

![image-20230213222017902](Oracle复习.assets/image-20230213222017902.png)

#### 异常的类型

![image-20230213222100005](Oracle复习.assets/image-20230213222100005.png)

##### 系统预定义异常

![image-20230213222135405](Oracle复习.assets/image-20230213222135405.png)

背不住的，差不多得了

![image-20230213222204903](Oracle复习.assets/image-20230213222204903.png)

##### 非预定义异常

![image-20230213222241642](Oracle复习.assets/image-20230213222241642.png)

多此一举

pragma exception_init(异常名,-2291)

![image-20230213222336327](Oracle复习.assets/image-20230213222336327.png)

##### 用户自定义异常

![image-20230213222650876](Oracle复习.assets/image-20230213222650876.png)

自己抛异常，自己抓

raise抛异常

![image-20230213222733674](Oracle复习.assets/image-20230213222733674.png)

### 触发器Trigger

#### 触发器创建语法

记得写replace

![image-20230213223804251](Oracle复习.assets/image-20230213223804251.png)

#### 语句级触发器

![image-20230213232849353](Oracle复习.assets/image-20230213232849353.png)

#### 行级触发器

语句级触发器是指一条SQL语句触发一次；

行级触发器是指一条SQL语句影响的每一行触发一次。

行级触发器可以用  :old和 :new，语句级不能用

![image-20230213233000391](Oracle复习.assets/image-20230213233000391.png)

##### 使用 :old和 :new

![image-20230213233051175](Oracle复习.assets/image-20230213233051175.png)

![image-20230213233445959](Oracle复习.assets/image-20230213233445959.png)

### 存储过程Procedure

#### 创建过程

记得写replace

is和as基本没区别

![image-20230213233713793](Oracle复习.assets/image-20230213233713793.png)

#### 调用过程

![image-20230213233821638](Oracle复习.assets/image-20230213233821638.png)

#### 过程的形参

![image-20230213234332979](Oracle复习.assets/image-20230213234332979.png)

in或out写在变量名和变量类型之间

##### 参数的缺省值 

![image-20230213234537371](Oracle复习.assets/image-20230213234537371.png)

default+默认值

#### 创建函数

函数有return，存储过程没有。

![image-20230213234609998](Oracle复习.assets/image-20230213234609998.png)

![image-20230213234757275](Oracle复习.assets/image-20230213234757275.png)

#### 调用函数

![image-20230213234832179](Oracle复习.assets/image-20230213234832179.png)