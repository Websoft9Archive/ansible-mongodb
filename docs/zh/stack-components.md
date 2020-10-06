# 参数

MongoDB 预装包包含 MongoDB 运行所需一序列支撑软件（简称为“组件”），下面列出主要组件名称、安装路径、配置文件地址、端口、版本等重要的信息。

## 路径

### MongoDB

MongoDB 数据目录: */var/lib/mongodb*  
MongoDB 配置文件: */etc/mongod.conf*  
MongoDB 日志文件: */var/log/mongodb*  

### adminMongo on Docker

adminMongo 采用 Docker 安装

Docker 根目录: */var/lib/docker*  
Docker 镜像目录: */var/lib/docker/image*  

## 端口号

在云服务器中，通过 **[安全组设置](https://support.websoft9.com/docs/faq/zh/tech-instance.html)** 来控制（开启或关闭）端口是否可以被外部访问。 

本应用建议开启的端口如下：

| 名称 | 端口号 | 用途 |  必要性 |
| --- | --- | --- | --- |
| adminMongo on Docker | 9091 | 通过 HTTP 访问 adminMongo | 可选 |
| MongoDB Server | 27017 | 远程连接 MongoDB | 可选 |

## 版本号

组件版本号可以通过云市场商品页面查看。但部署到您的服务器之后，组件会自动进行更新导致版本号有一定的变化，故精准的版本号请通过在服务器上运行命令查看：

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
