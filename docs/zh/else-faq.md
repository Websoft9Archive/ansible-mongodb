# FAQ

#### 什么是 MongoDB 的 Client 和 Server？

MongoDB Server 是指 MongoDB 程序本体，而 MongoDB Client 指采用TCP协议用于连接程序本地的客户端。它们是两个完全不同的程序，也就是说它们并需要同时安装到同一台服务上。

#### mongod 和 mongo 命令有什么区别？

mongod 是 MongoDB 的服务端管理命令，用于启动数据库服务  
mongo 是用于访问 MongoDB 服务的客户端  

#### MongoDB Community vs MongoDB Enterprise？

MongoDB Community is the source available and free to use edition of MongoDB.  
MongoDB Enterprise is available as part of the MongoDB Enterprise Advanced subscription and includes comprehensive support for your MongoDB deployment.   MongoDB Enterprise also adds enterprise-focused features such as LDAP and Kerberos support, on-disk encryption, and auditing.  

#### 是否可以不进行身份验证就直接访问 MongoDB？

可以，默认安装时 MongoDB 没有开启访问控制，无需MongoDB 用户名密码就可以访问，例如通过此URL访问：mongodb://localhost/admin。
 > MongoDB [访问控制参考](https://docs.mongodb.com/manual/tutorial/enable-authentication/)

#### MongoDB 中的 admin 数据库是什么？

安装 MongoDB 时会默认包含一个 admin 数据库，如果你创建管理员账户就必须存储到这个admin中

#### 是否可以修改 MongoDB 数据目录？

可以，通过修改 /etc/mongod.conf 配置文件

#### 数据库 root 用户对应的密码是多少？

密码存放在服务器相关文件中：`/credentials/password.txt`

#### 是否有可视化的数据库管理工具？

有，内置 [adminMongo](/zh/solution-gui.md#adminmongo)

#### MongoDB 提供哪些安全认证？

MongoDB provides various features, such as authentication, access control, encryption, to secure your MongoDB deployments. Some key security features include:

| Authentication | Authorization | TLS/SSL | Enterprise Only |
| :--- | :--- | :--- | :--- |
| [Authentication](https://docs.mongodb.com/manual/core/authentication/)<br />[SCRAM](https://docs.mongodb.com/manual/core/security-scram/)<br />[x.509](https://docs.mongodb.com/manual/core/security-x.509/) | [Role-Based Access Control](https://docs.mongodb.com/manual/core/authorization/)<br />[Enable Auth](https://docs.mongodb.com/manual/tutorial/enable-authentication/)<br />[Manage Users and Roles](https://docs.mongodb.com/manual/tutorial/manage-users-and-roles/) | [TLS/SSL (Transport Encryption)](https://docs.mongodb.com/manual/core/security-transport-encryption/)<br />[Configure mongod and mongos for TLS/SSL](https://docs.mongodb.com/manual/tutorial/configure-ssl/)<br />[TLS/SSL Configuration for Clients](https://docs.mongodb.com/manual/tutorial/configure-ssl-clients/) | [Kerberos Authentication](https://docs.mongodb.com/manual/core/kerberos/)<br />[LDAP Proxy Authentication](https://docs.mongodb.com/manual/core/security-ldap/)<br />[Encryption at Rest](https://docs.mongodb.com/manual/core/security-encryption-at-rest/)<br />[Auditing](https://docs.mongodb.com/manual/core/auditing/) |

> MongoDB also provides the [Security Checklist](https://docs.mongodb.com/manual/administration/security-checklist/) for a list of recommended actions to protect a MongoDB deployment.

#### MongoDB 支持哪些平台？

所支持的平台[参考](https://docs.mongodb.com/manual/administration/production-notes/#prod-notes-supported-platforms)

#### 部署和安装有什么区别？

部署是将一序列软件按照不同顺序，先后安装并配置到服务器的过程，是一个复杂的系统工程。  
安装是将单一的软件拷贝到服务器之后，启动安装向导完成初始化配置的过程。  
安装相对于部署来说更简单一些。 

#### 云平台是什么意思？

云平台指提供云计算服务的平台厂家，例如：Azure,AWS,阿里云,华为云,腾讯云等

#### 实例，云服务器，虚拟机，ECS，EC2，CVM，VM有什么区别？

没有区别，只是不同厂家所采用的专业术语，实际上都是云服务器
