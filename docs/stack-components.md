# Parameters

The MongoDB deployment package contains a sequence software (referred to as "components") required for MongoDB to run. The important information such as the component name, installation directory path, configuration file path, port, version, etc. are listed below.

## Path
You should know the components is different for different OS before using MongoDB/MariaDB

### Linux

#### MongoDB&MariaDB

MongoDB install directory: */usr/share/mongodb*  
MongoDB data directory: */data/mongodb*  
MongoDB Configuration File: */etc/my.cnf*  
MongoDB error log: */var/log/mongodb/mongodbd.log*  
MongoDB Process Identification Number: */run/mongodbd/mongodbd.pid*  
MongoDB Socket: */var/lib/mongodb/mongodb.sock*  

#### phpMyAdmin on Docker

Most of time, we used Docker to install phpMyAdmin

#### phpMyAdmin on PHP

For php runtime, e.g LAMP/LNMP, phpMyAdmin is an application for deployment   

phpMyAdmin installation directory: */data/apps/phpmyadmin*  
phpMyAdmin configuration file: */data/apps/phpmyadmin/config.inc.php*   
phpMyAdmin vhost configuration file: */etc/httpd/conf.d/phpMyAdmin.conf*   

### Windows Sever

#### MongoDB&MariaDB

Database install directory: */C:/websoft9/mongodb*  
Database data directory: */C:/websoft9/mongodb/data*  
Database configuration file: */C:/websoft9/mongodb/my.ini*  


## Ports

You can control(open or shut down) ports by **[Security Group Setting](https://support.websoft9.com/docs/faq/tech-instance.html)** of your Cloud Server whether the port can be accessed from Internet.

These ports should be opened for this application:

| Name | Number | Use |  Necessity |
| --- | --- | --- | --- |
| phpMyAdmin on Docker | 9090 | HTTP to visit phpMyAdmin | Optional |
| MongoDB | 3306 | remote connect MongoDB | Optional |
| MariaDB | 3306 | remote connect MariaDB | Optional |

## Version

You can see the version from product page of Marketplace. However, after being deployed to your server, the components will be automatically updated, resulting in a certain change in the version number. Therefore, the exact version number should be viewed by running the command on the server:

```shell
# Check all components version
sudo cat /data/logs/install_version.txt

# Linux Version
lsb_release -a

# MongoDB version
mongodb -V

# MongoDB Version
docker -v
```