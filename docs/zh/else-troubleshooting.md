# 故障处理

此处收集使用 MongoDB 过程中最常见的故障，供您参考

> 大部分故障与云平台密切相关，如果你可以确认故障的原因是云平台造成的，请参考[云平台文档](https://support.websoft9.com/docs/faq/zh/tech-instance.html)

#### 使用 /credentials/password.txt 中的账号密码无法登录？

可能密码修改没有成功，请使用[重置密码](/zh/solution-more.md#重置密码)

#### MongoDB数据库服务无法启动？

数据库服务无法启动最常见的问题包括：磁盘空间不足，内存不足，配置文件错误。  
建议先通过命令进行排查  

```shell
# 查看磁盘空间
df -lh

# 查看内存使用
free -lh

# 查看数据库状态以日志
systemctl status mongod
journalctl  -u mongod.service
```

#### 本地 MongoDB compass 无法连接数据库？

检查27017端口，bindIP和账户认证等连接字段是否满足条件