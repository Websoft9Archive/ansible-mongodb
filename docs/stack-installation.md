# Initial Installation

If you have completed the MongoDB deployment on Cloud Platform, the following steps is for you to start use it quikly

## Preparation

1. Get the **Internet IP** on your Cloud Platform
2. Check you **[Inbound of Security Group Rule](https://support.websoft9.com/docs/faq/tech-instance.html)** of Cloud Console to ensure the **TCP:27017 和TCP:9091** 

> 27017 if for MongoDB server, 9091 is for web GUI tool adminMongo

## MongoDB Initial verification

You should verify the MongoDB when completed deployment:

### Check MongoDB

1. Use the **SSH** to connect Server, and run the command below to view the installation information and running status
   ```
   sudo systemctl status mongod
   ```
2. You can ge the message from SSH " Active: active (running)... " when MongoDB is running

### Connect MongoDB

1. Use the **SSH** to connect Server, and run `mongo` command 
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

2. List all databases and users
   ```
   # list all databases
   show dbs

   # use admin, and list all users
   use admin
   show users
   ```

> More details about MongoDB, refer to official docs [MongoDB Administration](https://docs.mongodb.com/manual/administration/)

## Q&A

#### I can't visit adminMongo?

Your TCP:9091 of Security Group Rules is not allowed so there no response from Chrome or Firefox

#### Does MongoDB enable account authentication by default?

No, you should modify the configuration file */etc/mongod.conf* if you want 
