# More

Each of the following solutions has been proven to be effective and we hope to be helpful to you.

The data directory for MongoDB is set to /data/mongodb by default. If you want to modify MongoDB Data Directory, following are the steps for you:


## Enable the MongoDB remote connection

1. Use **SSH** to connect MongoDB server and modify the MongoDB configuration file: *etc/mongod.conf*
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


## Password management

### Modify password

You can modify the password of **root** user which added on your MongoDB by the following command

```
mongo admin --u root --p YOURPASSWORD
MongoDB shell version v4.0.18
connecting to: mongodb://127.0.0.1:27017/?gssapiServiceName=mongodb
> db = db.getSiblingDB('admin')
admin
> db.changeUserPassword("root", "NEWPASSWORD")
> exit
```

### Reset password

Reset password is the process of resetting a new password through special solutions in case the password has been forgotten.

1. Use **SSH** to connect MongoDB server and modify the MongoDB configuration file: *etc/mongod.conf*
   ```
   security:
   authorization: disabled
   ```
2. Restart the MongoDB service
   ```
   systemctl restart mongod
   ```
3. Run the MongoDB command to set new password
   ```
   mongo
   > db = db.getSiblingDB('admin')
   admin
   > db.changeUserPassword("root", "NEWPASSWORD")
   ```

4. Repeat step 1, but set authorization to disabled
5. Restart the MongoDB service again