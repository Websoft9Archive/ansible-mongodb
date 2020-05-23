# 图形化工具

MongoDB的图形化工具分为桌面版和Web版两种形式，每种形式的工具都有一些比较受欢迎的工具：

#### 桌面版
- [MongoDB Compass Community](https://www.mongodb.com/download-center/compass) - A free tool for developing with MongoDB and includes a subset of the features of Compass.
- [dbKoda](https://www.dbkoda.com/) - Cross-platform and open-source IDE
- [MongoHub](https://github.com/jeromelebel/MongoHub-Mac) - Mac native client
- [Mongotron](http://mongotron.io/) - Cross-platform and open-source client built with Electron
- [NoSQLBooster](https://nosqlbooster.com/) - Feature-rich but easy-to-use cross-platform IDE (formerly MongoBooster)
- [Nosqlclient](https://github.com/nosqlclient/nosqlclient) - Cross-platform, self hosted and easy to use management tool (formerly Mongoclient)
- [Robo 3T](https://github.com/Studio3T/robomongo) - Free, native and cross-platform shell-centric GUI (formerly Robomongo)
- [Studio 3T](https://studio3t.com/) - Cross-platform GUI, stable and powerful (formerly MongoChef)

#### Web 版

- [adminMongo](https://github.com/mrvautin/adminMongo) - Web-based user interface to handle connections and databases needs
- [mongo-express](https://github.com/mongo-express/mongo-express) - Web-based admin interface built with Express
- [mongoadmin](https://github.com/thomasst/mongoadmin) - Admin interface built with Django
- [mongri](https://github.com/dongri/mongri) - Web-based user interface written in JavaScript
- [Rockmongo](https://github.com/iwind/rockmongo) - PHPMyAdmin for MongoDB, sort of

下面以两种流行的工具为例，介绍如何使用图形化工具。

## 前置工作

使用图形化工具之前务必开启MongoDB的访问认证，并设立用户密码，以保证足够的安全性。  

1. 修改 MongDB 配置文件 *etc/mongod.conf*
   ```
   #1 将authorization由disabled设置为enabled
   security:
   authorization: enabled

   #2 将 bindIP 修改为 0.0.0.0 或 本地电脑公网IP
   net:
      port: 27017
      bindIp: 0.0.0.0
   ```
   > 0.0.0.0 代表任意公网IP均可访问

2. 重启MongoDB服务
   ```
   systemctl restart mongod
   ```
3. 开启服务器安全组 **TCP:27017** 端口，保证MongoDB服务可以被外部外网访问。

以上条件准备好之后，就可以根据选择合适的图形化界面工具

## adminMongo

adminMongo 是一款在线web版工具，默认已经安装到了MongoDB部署方案中

1. 开启服务器安全组 **TCP：9091** 端口

2. 本地电脑浏览器访问：*http://服务器公网IP:9091* 打开adminMongo界面
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/mongodb/adminmongo-connect001-websoft9.png)

3. 以连接字符串为例（这里的IP地址是公网IP）
   ```
   # 默认连接到config数据库
   mongodb://root:1cTFecwTEs@40.114.115.58
   # 默认连接到admin数据库
   mongodb://root:1cTFecwTEs@40.114.115.58/admin
   mongodb://parse:AxXFcV5zSz@40.114.115.58/parse
   ```

4. 开始连接
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/mongodb/adminmongo-connect002-websoft9.png)

5. 连接成功，进入 adminMongo 控制面板
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/mongodb/adminmongo-connect003-websoft9.png)

6. 使用完成后，请删除连接
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/mongodb/adminmongo-connect004-websoft9.png)

## MongoDB Compass

1. [下载](https://www.mongodb.com/products/compass)并安装 MongoDB Compass
2. 填写准确的字段，连接 MongoDB
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/mongodb/mongodbcompass001-websoft9.png)
3. 连接成功，进入控制台
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/mongodb/mongodbcompass002-websoft9.png)