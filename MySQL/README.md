### 官网下载免安装版

![](.\img\1.png)



### MySQL的配置

1. 以管理员身份打开终端
2. 打开MySQL所在路径的bin文件夹
3. 输入 `.\mysqld --install`  安装MySQL服务
4. 输入 `.\mysqld --initialize --console` 初始化MySQL (记住初始密码)
5. 



### 终端命令语句

```
mysqld --install	安装MySQL
mysqld --initialize --console	初始化MySQL
mysqld --remove mysql	卸载MySQL
net start/sopt mysql	启动/停止MySQL服务
mysql -u root -p	登录MySQL
```

### SQL语法

```sql
alter user 'root'@'localhost' identified by '修改密码'	--修改密码

show databeses;	--显示所有数据库
use DatabaseName;	--切换使用表
show tables;	--显示所有当前使用表的所有列
```

