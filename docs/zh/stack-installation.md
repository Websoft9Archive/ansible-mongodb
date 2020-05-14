# 初始化验证

在云服务器上部署 MongoDB 预装包之后，请参考下面的步骤快速入门。

## 准备

1. 在云控制台获取您的 **服务器公网IP地址** 
2. 从本地电脑远程连接 MongoDB，登录云控制台安全组中，检查 **Inbound（入）规则** 下的 **TCP:27017** 端口是否开启
3. 从可视化Web管理工具 adminMongo，登录云控制台安全组中，检查 **Inbound（入）规则** 下的 **TCP:9091** 端口是否开启

## MongoDB 初始化验证

部署 MongoDB 之后，依次完成下面的步骤，验证其可用性

### 检测 MongoDB 安装

1. 使用 SSH 连接 MongoDB 所在的服务器，运行下面的命令，查看 MongoDB 的安装信息和运行状态
   ```
   sudo systemctl status mongod
   ```
2. 运行服务状态查询命令，MongoDB 正常运行会得到 " Active: active (running)... " 的反馈

镜像安装完成后，MongoDB就可以使用了。使用MongoDB有两种方式方式

### 命令方式连接 MongoDB

1. 使用 SHH 登录到 MongoDB 所在的服务器，运行 `mongo` 命令（MongoDB Shell）
   ~~~
   mongo

   ---
   MongoDB shell version v4.0.18
   connecting to: mongodb://127.0.0.1:27017/?gssapiServiceName=mongodb
   Implicit session: session { "id" : UUID("e5c50eca-e51b-482e-b0bd-24edc2d1e433") }
   MongoDB server version: 4.0.18
   Welcome to the MongoDB shell.
   For interactive help, type "help".
   For more comprehensive documentation, see
         http://docs.mongodb.org/
   Questions? Try the support group
         http://groups.google.com/group/mongodb-user
   ~~~

2. 分别列出默认数据库和用户
   ```
   ```

### phpMyAdmin 连接 MongoDB

如果部署方案中包含 phpMyAdmin 等图形化工具，使用就更加便捷方便：

1. 本地浏览器 Chrome 或 Firefox 访问：*http://服务器公网IP:9090*，进入phpMyAdmin
  ![登录phpMyadmin](https://libs.websoft9.com/Websoft9/DocsPicture/zh/mongodb/phpmyadmin-logincn-websoft9.png)
2. 输入数据库用户名和密码([不知道密码？](/zh/stack-accounts.md#mongodb))
3. 开始管理数据库
  ![phpMyadmin](https://libs.websoft9.com/Websoft9/DocsPicture/zh/mongodb/phpmyadmin-adddb-websoft9.png)

> 需要了解更多 phpMyAdmin 的使用，请参考本文档 [phpMyAdmin 章节](/zh/solution-phpmyadmin.md)

## 常见问题

#### 浏览器无法访问 phpMyAdmin（白屏没有结果）？

您的服务器对应的安全组9090端口没有开启（入规则），导致浏览器无法它

#### phpMyAdmin 是如何安装的？

采用 Docker 安装，保证 MongoDB 环境具有良好的隔离性。