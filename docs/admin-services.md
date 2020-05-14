# Start or Stop the Services

These commands you must know when you using the MongoDB of Websoft9

## Linux

### MongoDB
```shell
#For CentOS&Redhat
sudo systemctl start mongodbd
sudo systemctl restart mongodbd
sudo systemctl stop mongodbd
sudo systemctl status mongodbd

#For Ubuntu&Debian
sudo systemctl start mongodb
sudo systemctl restart mongodb
sudo systemctl stop mongodb
sudo systemctl status mongodb
```

### MariaDB
```shell
systemctl start mariadb
systemctl stop mariadb
systemctl restart mariadb
```

### Docker

```shell
sudo systemctl start docker
sudo systemctl restart docker
sudo systemctl stop docker
sudo systemctl status docker
```

## Windows

For Windows Sever, please use the system's services management to start | stop | restart MongoDB  
![](https://libs.websoft9.com/Websoft9/DocsPicture/en/mongodb/mongodb-servicewin-websoft9.png)