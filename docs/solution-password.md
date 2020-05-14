# Modify and reset MongoDB password

Modify password: Change the current password to another password  
Reset password: Have forgotten your password, need to get an initial password

## Modify password

You can modify password by MongoDB GUI or commands:

### Use phpMyAdmin(Recommend) 

![](http://libs.websoft9.com/Websoft9/DocsPicture/zh/mongodb/websoft9-modifymongodbpw.gif)

### Use commands
```
mongodbadmin -u root -p oldpassword password 'newpassword' 
```

## Reset password

You can reset your MongoDB password by the following two solution:  

### Quick Plan(Recommend) 

1. Use SSH to connect MongoDB Server
2. Run the following command
   ```
   sudo git clone https://github.com/Websoft9/linux.git; cd linuxscript/Mysql\_ResetPasswd\_Script;sudo sh reset\_mongodb\_password.sh
   ```
### Manual solution

1. Use SSH to connect MongoDB Server
2. Stop MongoDB
   ~~~
   sudo systemctl stop mongodbd
   ~~~
3. Use the safe mode to restart MongoDB
   ~~~
   sudo mongodbd_safe --skip-grant-tables &
   ~~~
4. Reset password(e.g reset password to `123456`)
   ~~~
   sudo mongodb -e "use mongodb;update user set password=password('123456') where user='root';"
   ~~~
5. Shut down MongoDB service
   ~~~
   sudo kill all mongodbd
   ~~~ 
6. Start MongoDB service
   ~~~
   sudo systemctl start mongodbd
   ~~~