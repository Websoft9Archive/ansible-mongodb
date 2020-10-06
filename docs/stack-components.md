# Parameters

The MongoDB deployment package contains a sequence software (referred to as "components") required for MongoDB to run. The important information such as the component name, installation directory path, configuration file path, port, version, etc. are listed below.

## Path

You should know the components is different for different OS before using MongoDB

### MongoDB

MongoDB data directory: */var/lib/mongodb*  
MongoDB Configuration File:  */etc/mongod.conf*  
MongoDB logs File:  */var/log/mongodb*  

### adminMongo on Docker

adminMongo installed by Docker

Docker root directory: */var/lib/docker*  
Docker image directory: */var/lib/docker/image*  


## Ports

You can control(open or shut down) ports by **[Security Group Setting](https://support.websoft9.com/docs/faq/tech-instance.html)** of your Cloud Server whether the port can be accessed from Internet.

These ports should be opened for this application:

| Name | Number | Use |  Necessity |
| --- | --- | --- | --- |
| adminMongo on Docker | 9091 | HTTP to visit adminMongo | Optional |
| MongoDB Server | 27017 | remote connect MongoDB | Optional |

## Version

You can see the version from product page of Marketplace. However, after being deployed to your server, the components will be automatically updated, resulting in a certain change in the version number. Therefore, the exact version number should be viewed by running the command on the server:

```shell
# Check all components version
sudo cat /data/logs/install_version.txt

# Linux Version
lsb_release -a

# MongoDB version
mongodb -V

# Docker Version
docker -v
```
