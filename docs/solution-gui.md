# GUI

MongoDB的图形化工具分为桌面版和Web版两种形式，每种形式的工具都有一些比较受欢迎的工具：

#### Desktop
- [MongoDB Compass Community](https://www.mongodb.com/download-center/compass) - A free tool for developing with MongoDB and includes a subset of the features of Compass.
- [dbKoda](https://www.dbkoda.com/) - Cross-platform and open-source IDE
- [MongoHub](https://github.com/jeromelebel/MongoHub-Mac) - Mac native client
- [Mongotron](http://mongotron.io/) - Cross-platform and open-source client built with Electron
- [NoSQLBooster](https://nosqlbooster.com/) - Feature-rich but easy-to-use cross-platform IDE (formerly MongoBooster)
- [Nosqlclient](https://github.com/nosqlclient/nosqlclient) - Cross-platform, self hosted and easy to use management tool (formerly Mongoclient)
- [Robo 3T](https://github.com/Studio3T/robomongo) - Free, native and cross-platform shell-centric GUI (formerly Robomongo)
- [Studio 3T](https://studio3t.com/) - Cross-platform GUI, stable and powerful (formerly MongoChef)

#### Web GUI

- [adminMongo](https://github.com/mrvautin/adminMongo) - Web-based user interface to handle connections and databases needs
- [mongo-express](https://github.com/mongo-express/mongo-express) - Web-based admin interface built with Express
- [mongoadmin](https://github.com/thomasst/mongoadmin) - Admin interface built with Django
- [mongri](https://github.com/dongri/mongri) - Web-based user interface written in JavaScript
- [Rockmongo](https://github.com/iwind/rockmongo) - PHPMyAdmin for MongoDB, sort of

Now, we will introduce how to use **MongoDB compass** and **adminMongo**

## Preparation

You must enable the authorization of MongoDB and set credential for it before your using the GUI  

1. Use **SSH** to connect MongoDB server and modify the MongDB configuration file *etc/mongod.conf*
   ```
   #1 set authorization **disabled** to **enabled**
   security:
   authorization: enabled

   #2 set bindIP to 0.0.0.0
   net:
      port: 27017
      bindIp: 0.0.0.0
   ```
   > 0.0.0.0 means any Internet IP can connect your MongoDB

2. Restart MongoDB service
   ```
   systemctl restart mongod
   ```
3. Go to the Cloud Console and enable the **TCP:27017** port of Security Group

When completed the preparation, you can use the GUI now

## adminMongo

adminMongo is a web GUI which installed by Docker for your MongoDB deployment solution

1. Go to the Cloud Console and enable the **TCP:9091** port of Security Group

2. Open Chrome or Firefox on your local PC to visit URL *http://Internet IP:9091*,you can enter the adminMongo page
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/mongodb/adminmongo-connect001-websoft9.png)

3. Following is the examples for adminMongo connection(IP is Internet IP0)
   ```
   # use the **config** database
   mongodb://root:1cTFecwTEs@40.114.115.58
   # use the **admin** database
   mongodb://root:1cTFecwTEs@40.114.115.58/admin
   mongodb://parse:AxXFcV5zSz@40.114.115.58/parse
   ```

4. Start to connect
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/mongodb/adminmongo-connect002-websoft9.png)

5. Go go adminMongo console when connect successfully
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/mongodb/adminmongo-connect003-websoft9.png)

6. Please delete the connections when you don't use it
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/mongodb/adminmongo-connect004-websoft9.png)

## MongoDB Compass

1. [Download](https://www.mongodb.com/products/compass) and install MongoDB Compass
2. Fill in the correct items and connect MongoDB
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/mongodb/mongodbcompass001-websoft9.png)
3. Go go MongoDB Compass console when connect successfully
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/mongodb/mongodbcompass002-websoft9.png)