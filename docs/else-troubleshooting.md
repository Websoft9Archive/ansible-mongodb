# Troubleshooting

We collect the most common troubleshooting of using MongoDB for your reference:

> Many troubleshooting is closely related to the Server, if you can confirm troubleshooting is related to Cloud Platform, please refer to [Cloud Platform Documentation](https://support.websoft9.com/docs/faq/tech-instance.html)


#### MongoDB is no running?

The most common reasons why MongoDB can't start include: insufficient disk space, insufficient memory, configuration file errors... If you application can not connect the MongoDB, please refer to following step to solve the problem

1. Using the `systemctl status mongodbd` command to view the MongoDB status
```powershell
[root@izm5e5otogu0m1fktk1gsyz ~]# systemctl status mongodbd
● mongodbd.service - MongoDB Community Server
   Loaded: loaded (/usr/lib/systemd/system/mongodbd.service; enabled; vendor preset: disabled)
   Active: inactive (dead) since Thu 2019-04-04 11:09:32 CST; 15s ago
  Process: 25155 ExecStartPost=/usr/bin/mongodb-systemd-start post (code=exited, status=0/SUCCESS)
  Process: 25154 ExecStart=/usr/bin/mongodbd_safe --basedir=/usr (code=exited, status=0/SUCCESS)
  Process: 25140 ExecStartPre=/usr/bin/mongodb-systemd-start pre (code=exited, status=0/SUCCESS)
 Main PID: 25154 (code=exited, status=0/SUCCESS)

```

2. You can find the message "Active: inactive (dead) since Thu 2019-04-04 11:09:32 CST; 15s ago" , it means MongoDB is not running now
2. Using the `systemctl start mongodbd` to start MongoDB, If started successfully, the problem has beed solved
2. Otherwise, you should analysis MongoDB logs _/var/log/mongodbd.log_ to found the reason

#### Database service could not be started?

Insufficient disk space, insufficient memory, and configuration file errors can make database service could not be started  

It is recommended to first check through the command.

```shell
# restart mongodb service
systemctl restart mongodb

# view disk space
df -lh

# view memory rate
free -lh
```

#### The database log file is too large, resulting in insufficient disk space?

By default, mongodb will automatically open the binlog. Binlog is mainly used to recover the database without backup. However, the binlog will take up a lot of space. If you don't clean it for a long time, the remaining disk space will be 0, which will affect the database or the server will not start.

If you have confidence in your own backup, you do not need the binlog function. Refer to the following steps to turn it off:

1. Edit [MongoDB Configuration File] (/stack-components.md#mongodb) and comment out the binlog log   
```
#log-bin=mongodb-bin
```
2. Restart mongodb
```
systemctl restart mongodbd
```
#### phpMyAdmin page access blank?

Please try another browser, such as chrome or firefox. If the phpMyAdmin can be opened normally before, and now appears to be incomplete or blank, it is recommended to clean up the browser cache, cookies and other information

#### The container fails to start?

The most common reason is that the user did not set the required environment variables according to the requirements of the container, causing the container to fail to start

#### Container port mapping failed?

If the user is unable to grasp the mapping relationship and availability between the host (server) operating system port and the container port, please enable automatic port mapping