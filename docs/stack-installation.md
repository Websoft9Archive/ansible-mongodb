# Initial Installation

If you have completed the MongoDB deployment on Cloud Platform, the following steps is for you to start use it quikly

## Preparation

1. Get the **Internet IP** on your Cloud Platform
2. Check you **[Inbound of Security Group Rule](https://support.websoft9.com/docs/faq/tech-instance.html)** of Cloud Console to ensure the TCP:9090 is allowed if you using the phpMyAdmin on Docker
3. Check you **[Inbound of Security Group Rule](https://support.websoft9.com/docs/faq/tech-instance.html)** of Cloud Console to ensure the TCP:3306 is allowed if you want to connect MongoDB from local GUI tools

## MongoDB Installation Wizard

### Check MongoDB

1. Use the **SSH** to connect Server, and run these command below to view the installation information and running status
   ```
   sudo systemctl status mongodbd
   #### or ####
   sudo systemctl status mongodb
   ```
2. You can ge the message from SSH " Active: active (running)... " when MongoDB is running

Then, you can login MongoDB 

### Login MongoDB with commands

1. Using SSH to connect MongoDB Server(or remote to Windows Server), run the following command
   ~~~
   #assume the root password is `123456`
   mongodb -uroot –p123456
   ~~~

2. You can find the MongoDB version from the message
   ![](http://libs.websoft9.com/Websoft9/DocsPicture/en/mongodb/mongodb01.png)


### Login MongoDB with phpMyAdmin

If you used the deployment solution included the phpMyAdmin, the database management is very easy

1. Using local Chrome or Firefox to visit the URL *http://Internet IP:9090* to visit phpMyAdmin
  ![login phpMyadmin](https://libs.websoft9.com/Websoft9/DocsPicture/en/mongodb/mongodb-login-websoft9.png)
2. Input your database account([Don't know password?](/stack-accounts.md#mongodb))
3. Start using phpMyAdmin to modify root password of MongoDB
  ![phpMyadmin](http://libs.websoft9.com/Websoft9/DocsPicture/en/phpmyadmin/phpmyadmin-changepwds-websoft9.png)

> More useful phpMyAdmin guide, please refer to [phpMyAdmin chapter](/solution-phpmyadmin.md) of this documentation



## Q&A

#### I can't visit the phpMyAdmin?

Your TCP:9090 of Security Group Rules is not allowed so there no response from Chrome or Firefox

#### How phpMyAdmin installed?

Install phpMyadmin used Docker, that can make sure MongoDB environment has good isolation
