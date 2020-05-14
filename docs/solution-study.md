
## MongoDB commands

Using SSH to connect to Linux or Windows-CMD of Remote Windows Server,then run the following command to connect MongoDB

### Connect MongoDB Server
~~~
mongodb -u root –p
Enter password:

#exit mongodb if you want
mongodb> exit  
~~~

### Useful commands

The following are the most commonly used mongodb command operations
```
#connect mongodb as root,then input your password
mongodb -u root -p

#show all databases
mongodb> show  databases;

#delete the the database of dbname
mongodb> drop database dbname;

#Create a new database
mongodb> create database DATABASE_NAME;

#Create a new user (only with local access) and grant privileges to this user on the new database:
mongodb> grant all privileges on DATABASE_NAME.* TO 'USER_NAME'@'localhost' identified by 'PASSWORD';

#Create a new user (with remote access) and grant privileges to this user on the new database
mongodb> grant all privileges on DATABASE_NAME.* TO 'USER_NAME'@'%' identified by 'PASSWORD';

#exit the mongodb mode
mongodb> exit
```


## MongoDB GUI tools

Working on a relational database using only command line tools to writing queries can be hard, luckily we found the best Free GUI tools for your MongoDB work. Most uses of MongoDB for Web development allow you to get around a lot of back end requirements with the use of PHP and other tools that work the database without having to do more than set up. However, as the use of SQL for Web development has increased, and the complexities, so has the availability of tools to manage your SQL database. Here are some of the best tools for working with your MongoDB database.



| **Name**                                                     | **Description**                                              | **Cross platform**                            | **Price** |
| ------------------------------------------------------------ | ------------------------------------------------------------ | --------------------------------------------- | --------- |
| [MongoDB Workbench](https://dev.mongodb.com/downloads/workbench/) | MongoDB Workbench is a unified visual tool for database architects, developers, and DBAs. MongoDB Workbench provides data modeling, SQL development, and comprehensive administration tools for server configuration, user administration, backup, and much more. | Windows,Linux,MacOS                           | Free      |
| [phpMyAdmin](https://www.phpmyadmin.net/)                    | phpMyAdmin is a free software tool written in PHP, intended to handle the administration of MongoDB over the Web. phpMyAdmin supports a wide range of operations on MongoDB and MariaDB. Frequently used operations (managing databases, tables, columns, relations, indexes, users, permissions, etc) can be performed via the user interface, while you still have the ability to directly execute any SQL statement. | Based on Web,one installation, use everywhere | Free      |
| [Navicat](https://www.navicat.com/en/products/navicat-for-mongodb) | Navicat for MongoDB is the ideal solution for MongoDB/MariaDB administration and development. It is a single application that allows you to connect to MongoDB and MariaDB databases simultaneously. | Windows,MacOS,IOS                             | Not free  |
| [MongoDB-Front](http://www.mongodbfront.de/)                     | MongoDB-Front is a Windows front end program for the MongoDB database server. The database structure and data can be handled via dialogs or SQL commands. Import and Export in standard file formats is supported. The database server can be connected directly or via HTTP tunneling. | Windows                                       | Free      |
| [Sequel Pro](https://sequelpro.com/)                         | Sequel Pro is a fast, easy-to-use Mac database management application for working with MongoDB databases. | MacOS                                         | Free      |
| [HeidiSQL](https://www.heidisql.com/download.php)            | HeidiSQL is a useful and reliable tool designed for web developers using the popular MariaDB or MongoDB server, Microsoft SQL databases or PostgreSQL. Support for multiple languages (including Chinese) | Windows                                       | Free      |
| [DBeaver Community](https://dbeaver.io/)                     | Free multi-platform database tool for developers, SQL programmers, database administrators and analysts. Supports all popular databases: MongoDB, PostgreSQL, MariaDB, SQLite, Oracle, DB2, SQL Server, Sybase, MS Access, Teradata, Firebird, Derby, etc. | Windows                                       | Free      |
| [dbForge Studio for MongoDB Express](https://www.devart.com/dbforge/mongodb/) | dbForge Studio for MongoDB is a universal GUI tool for MongoDB and MariaDB database development, management, and administration. The IDE allows you to create and execute queries, develop and debug stored routines, automate database object management, analyze table data via an intuitive interface. The MongoDB client delivers data and schema comparison and synchronization tools, database reporting tools, backup options with scheduling, and much more. | Windows                                       | Free      |



GUI tools gives you direct access to your MongoDB Databases on local and remote servers.
