# 服务启停

使用由 Websoft9 提供的 MongoDB 部署方案，可能需要用到的服务如下：

## Linux系统

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

## Windows 系统

Windows下的镜像采用操作系统的服务管理功能，来实现 MongoDB 的启动、停止和重启操作
![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/mongodb/mongodb-servicewin-websoft9.png)