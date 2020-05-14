# MongoDB速学

### 连接 MongoDB Server

~~~
mongodb -u root –p
Enter password:

#exit mongodb if you want
mongodb> exit  
~~~

## 常见命令

```

MongoDB [(none)]> create database 数据库名称;     #特别注意有分号

MongoDB [(none)]>  show  databases;                      #查看数据库

MongoDB [(none)]>  exit;                                 #退出数据库控制台，特别注意有分号

MongoDB [(none)]> drop database 数据库名称;     #删除数据库

MongoDB [(none)]> exit;                                     #退出数据库控制台，特别注意有分号

MongoDB [(none)]> show databases;           #查看数据库: 如下图中3个数据库是默认数据库，不可删除

```
![websoft9-mongodb](http://libs.websoft9.com/Websoft9/DocsPicture/zh/mongodb/mongodb_databases_default.png)
