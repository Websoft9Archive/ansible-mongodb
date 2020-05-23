# MongoDB shell

MongoDB Shell 是 MongoDB 自带的一个交互式 JavaScript shell，让您能够访问、配置和管理MongoDB数据库、用户等。使用这个shell可执行各种任务，从设置用户账户到创建数据库，再到查询数据库内容，无所不包。

### 启动 MongoDB shell

使用 Websoft9 提供的 MongoDB 部署方案，默认已经配置好了环境变量。只需登录服务器，运行`mongo`命令，即可进入 MongoDB shell

```shell
# log in Mongo Shell without authenticating
mongo

# log in Mongo Shell witt authenticating
mongo admin --username root -p


MongoDB Enterprise > help
        db.help()                    help on db methods
        db.mycoll.help()             help on collection methods
        sh.help()                    sharding helpers
        rs.help()                    replica set helpers
        help admin                   administrative help
        help connect                 connecting to a db help
        help keys                    key shortcuts
        help misc                    misc things to know
        help mr                      mapreduce

        show dbs                     show database names
        show collections             show collections in current database
        show users                   show users in current database
        show profile                 show most recent system.profile entries with time >= 1ms
        show logs                    show the accessible logger names
        show log [name]              prints out the last segment of log in memory, 'global' is default
        use <db_name>                set current database
        db.foo.find()                list objects in collection foo
        db.foo.find( { a : 1 } )     list objects in foo where a == 1
        it                           result of the last line evaluated; use to further iterate
        DBQuery.shellBatchSize = x   set default number of items to display on shell
        exit                         quit the mongo shell

```


### 常见命令

#### 显示、创建和切换数据库

```shell

> show dbs
admin     0.000GB
config    0.000GB
local     0.000GB

# 创建test数据库（如果不存在test数据库，就会自动创建它）
> use test
switched to db test

# 显示当前数据库
> db
test

# 显示当前所有用户数据
> show users

#3 插入数据到数据库
> db.test.insert({"name":"company"})
WriteResult({ "nInserted" : 1 })
```


#### 删除数据库
```
> show dbs
admin     0.000GB
config    0.000GB
local     0.000GB
test      0.000GB
websoft9  0.000GB

> use test
switched to db test
> use test
> db.dropDatabase()
{ "dropped" : "test", "ok" : 1 }
> show dbs
admin     0.000GB
config    0.000GB
local     0.000GB
websoft9  0.000GB
```

#### 创建管理员账号

```
> mongo
> use admin
switched to db admin
> db.createUser( { user: "webs_admin", pwd: "websoft9", roles: ["userAdminAnyDatabase"] } )
Successfully added user: { "user" : "webs_admin", "roles" : [ "userAdminAnyDatabase" ] }


# 显示账号
> show users
{
        "_id" : "admin.webs_admin",
        "user" : "webs_admin",
        "db" : "admin",
        "roles" : [
                {
                        "role" : "userAdminAnyDatabase",
                        "db" : "admin"
                }
        ],
        "mechanisms" : [
                "SCRAM-SHA-1",
                "SCRAM-SHA-256"
        ]
}
```