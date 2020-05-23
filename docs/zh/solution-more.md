# 更多...

下面每一个方案，都经过实践证明行之有效，希望能够对你有帮助

## 开启远程访问

1. 修改 MongDB 配置文件 *etc/mongod.conf*
   ```
   #1 将authorization由disabled设置为enabled
   security:
   authorization: enabled

   #2 将 bindIP 修改为 0.0.0.0 或 本地电脑公网IP
   net:
      port: 27017
      bindIp: 0.0.0.0
   ```
   > 0.0.0.0 代表任意公网IP均可访问

2. 重启MongoDB服务
   ```
   systemctl restart mongod

## 密码管理

### 修改密码

参考下面的命令，修改已经创建的管理员账号root的密码

```
mongo admin --u root --p YOURPASSWORD
MongoDB shell version v4.0.18
connecting to: mongodb://127.0.0.1:27017/?gssapiServiceName=mongodb
> db = db.getSiblingDB('admin')
admin
> db.changeUserPassword("root", "NEWPASSWORD")
> exit
```

### 重置密码

重置密码即已经忘记密码的情况下，通过特殊手段重新设置新密码的过程。

1. 修改 MongDB 配置文件 *etc/mongod.conf*，将authorization由disabled设置为enabled
   ```
   security:
   authorization: disabled

   ```
2. 重启MongoDB服务
   ```
   systemctl restart mongod
   ```
3. 重新设置密码
   ```
   mongo
   > db = db.getSiblingDB('admin')
   admin
   > db.changeUserPassword("root", "NEWPASSWORD")
   ```

4. 重复第1步，但将authorization由enabled设置为disabled
5. 重启MongoDB服务