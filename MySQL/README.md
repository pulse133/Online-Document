## 官网下载免安装版<img src=".\img\1.png">

[下载地址](https://dev.mysql.com/downloads/mysql/)	[图片8.1.0版本](https://cdn.mysql.com//Downloads/MySQL-8.1/mysql-8.1.0-winx64.zip)



## MySQL的配置

1. 以管理员身份打开终端
2. 打开MySQL所在路径的bin文件夹
3. 输入 `.\mysqld --install`  安装MySQL服务
4. 输入 `.\mysqld --initialize --console` 初始化MySQL (记住初始密码)



## 终端命令语句

```
mysqld --install	安装MySQL
mysqld --initialize --console	初始化MySQL
mysqld --remove mysql	卸载MySQL
net start/sopt mysql	启动/停止MySQL服务
mysql -u root -p	登录MySQL
```



## 基础语法

```mysql
alter user 'root'@'localhost' identified by '修改密码'	--修改密码

show databeses;	-- 显示所有数据库

use DatabaseName;	-- 切换使用表
show tables;		-- 显示当前进入的数据库中的所有表

create database db1;	-- 创建数据库 db1
drop database db1;	-- 删除数据库 db1
alter database db1 charset utf8;	-- 修改数据库

select database();	-- 显示当前所在文件夹

show status;	-- 显示数据库状态
```



## 三种注释方式

```mysql
-- 注释1
# 注释2
/* 注释3 */
```



## 表语法

```mysql
desc t_name;	-- 查看表 t_name 的结构
drop table t_name	-- 删除表 t_name 
create table t_name (
    属性名 数据类型 约束条件,
    属性名 数据类型 约束条件,
    属性名 数据类型 约束条件,
    ...
);
```

#### 约束条件

```mysql
primary key		-- 主键
foreign key		-- 外键
not null	-- 不能为空
unique	-- 唯一 不能重复
auto_increment	-- 自增
default	-- 设置默认值
```

#### 表的修改

```mysql
alter table old_table rename new_table;	-- 修改表名称
alter table t_name modify 属性名 数据类型;	-- 修改表字段的数据类型
alter table t_name change 旧属性名 新属性名 新数据类型;	-- 修改新的字段名和属性数据类型
alter table t_name add 属性名 数据类型 [条件约束...];	-- 增加新字段
alter table t_name drop 属性名;	-- 删除字段

```

#### 增删改查

```mysql
insert into t_name (字段名) value(v1, v2, v3);	-- 增 字段名可有可无
insert into t_name () value(v1, v2, v3), (v1, v2, v3)...;

delete from t_name where 条件;	-- 删
delete from t_nmae;	-- 删除表 t_name 的所有数据

update t_name set 字段名1=值, 字段名2=值 where 条件;	-- 修改内容
update t_name set 字段名1=值;

select * from t_name;	-- 查看表 t_name 的所有内容
select * from t_name where id in (1,2,3);	-- 查询id是(1,2,3)的列
select * from t_name where uname is not null;	-- 查询uname内容为 null 的行
select * from t_name where id not between 2 and 10;	-- 查询id不在[2, 10]的行
select distinct gender from t_name;	-- 返回结果不管有多少个重复的只显示一个
select * from t_table where uname like "%狗";	-- % 匹配多个
select  * from t_table where id=1 and uname='二狗';	-- and 并且 匹配多个条件
select * from t_table where id=1 and uname="二狗" or uname="狗大";	-- or 或者
```

#### like

| 字符 |   含义   |
| :--: | :------: |
|  %   | 匹配多个 |
|  _   | 匹配单个 |

#### 聚合函数

|  函数   |         含义         |
| :-----: | :------------------: |
| count() |      返回总行数      |
|  sum()  | 对返回的列的数值求和 |
|  avg()  |      返回平均值      |
|  max()  |      返回最小值      |
|  min()  |      返回最大值      |

```mysql
select count(*) from t_table;
select sum(id) from t_table;
select avg(id) from t_table;
select max(id) from t_table;
select min(id) from t_table;
```

