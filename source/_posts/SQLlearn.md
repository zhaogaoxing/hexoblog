---
title: SQL笔记
tags: SQL学习
categories: 程序员必备
---
# 啥子是SQL？
SQL指结构化查询语言Structured Query Language
SQL使我们有能力方位数据库
SQL是一种ANSI的标准计算机语言

可以把SQL分为两个部分：数据操作语言（DML）和数据定义语言（DDL）
SQL的DML部分：
SELECT -从数据库表中获取数据
UPDATE -更新数据库表中的数据
DELETE -从数据库表中删除数据
INSERT INTO -从数据库表中插入数据

SQL中重要的DDL语句：
CREATE DATABASE -创建新数据库
ALTER DATABASE -修改数据库
CREATE TABLE -创建新表
ALTER TABLE -变更数据库表
DROP TABLE -删除表
CREATE INDEX -创建索引
DPOP INDEX -删除索引
SQL对大小写不敏感
基本公式：
动词 + 要查询的数据项 + from + 表名 + where + 数据项  

# 对应数据库
表：记录的集合。
字段：记录中的一个数据项称为字段。
数据项：数据项也称为分量，是数据库中可以命名的最小逻辑数据单位，
指某个元组对应列的属性值，用来描述属性的数据。
主键：即为主码。
记录：指的是关系中的一行数据，用它描述实体。它是数据项的有序集，即
一个记录是由若干个数据项组成。
## 数据库中常用类型
如图：
字符类型：
![%E6%95%B0%E6%8D%AE%E5%BA%93%E4%B8%AD%E7%9A%84%E7%B1%BB%E5%9E%8B](http://obmrysrv0.bkt.clouddn.com/%E6%95%B0%E6%8D%AE%E5%BA%93%E4%B8%AD%E7%9A%84%E7%B1%BB%E5%9E%8B.png)
时间类型（特有的）：
![SQLtime](http://obmrysrv0.bkt.clouddn.com/SQLtime.png)


# 表的创建和使用
选择连接中的一个数据库右击，选择命令列界面，输入如下：
![SQLcreatetable1](http://obmrysrv0.bkt.clouddn.com/SQLcreatetable1.png)
然后刷新就可以看到创建的数据表了（我的还需要断开连接不知道为啥）

## 使用命令列insert into 插入
insert into 表名（属性列）
values（值）
![SQLinsertINTO](http://obmrysrv0.bkt.clouddn.com/SQLinsertINTO.png)
然后打开表zhao就可以看到添加的数据了
当然表名后面的属性列可以省略，但是values的值必须全不为空，切记

## 数据操控
数据操控 + from表名 + where条件
查询：select * from zhao where name = 'zz';
![SQLselect](http://obmrysrv0.bkt.clouddn.com/SQLselect.png)
更新：update zhao set name = 'aa' where id = 666;
![SQLUPDATE](http://obmrysrv0.bkt.clouddn.com/SQLUPDATE.png)
删除：delete from zhao where name ='zz';
![SQLdelete](http://obmrysrv0.bkt.clouddn.com/SQLdelete.png)
![sqlupde](http://obmrysrv0.bkt.clouddn.com/sqlupde.png)

### select 查询语句
select  列名
from    表名
where   约束的条件
1.单表查询
查询时可以使用一些条件语句来怎么加查询的准确性和多样查询的功能
多重条件查询
 限制条件

其中between and包括边界值
not between and不包括边界值，他们互补
#### 多表查询
多表的连接查询
select * from A,B  where A.a = B.b;
多表的嵌套查询
动词 + 要查询的数据项 + from + 表名 + where + 数据项 = （SELECT语句）；
select * from A where a = (select * from B where b ='0');
只要带有where语句的，都可以添加嵌套操作
update：
update zhao set name ='id' where acc_id=(select id from B where b = 'zz');
delete也同理可以 

# 未完待续
![alonelyman1](http://obmrysrv0.bkt.clouddn.com/alonelyman1.jpg)