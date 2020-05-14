# 修改或重置 MongoDB 密码

修改密码，即使用已有密码登录MongoDB，然后修改成另外一个密码  
重置密码，即忘记了密码，需要通过重置密码找回

## 修改密码

可以通过MongoDB管理工具修改密码，也通过命令上修改密码

### phpMyAdmin修改密码

![](http://libs.websoft9.com/Websoft9/DocsPicture/zh/mongodb/websoft9-modifymongodbpw.gif)

### 命令行修改密码

执行一下命令:
```
mongodbadmin -u 用户名 -p 旧密码 password '新密码' 
```

## 重置密码

如果忘记了root密码，就需要通过命令操作，实现MongoDB密码重置。下面有两种方案可供使用：

### 快捷方案（推荐）

1. 使用SSH远程连接到MongoDB服务器
2. 运行如下命令，按提示输入新密码即可。
   ```
   sudo git clone https://github.com/Websoft9/linux.git; cd linuxscript/Mysql\_ResetPasswd\_Script;sudo sh reset\_mongodb\_password.sh
   ```
### 手动方案

1. 使用SSH远程连接到MongoDB服务器
2. 停止 MongoDB 服务
   ~~~
   systemctl stop mongodbd
   ~~~
3. 采用命令行参数启动mongodb 
   ~~~
   mongodbd_safe --skip-grant-tables &
   ~~~
4. 重置密码（这里将密码重置为`123456`）
   ~~~
   mongodb -e "use mongodb;update user set password=password('123456') where user='root';"
   ~~~
5. 关闭MongoDB进程
   ~~~
   kill all mongodbd
   ~~~ 
6. 启动MongoDB服务
   ~~~
   systemctl start mongodbd
   ~~~