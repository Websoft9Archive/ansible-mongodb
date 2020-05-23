# MongoDB shell

The mongo shell is an interactive JavaScript interface to MongoDB. You can use the mongo shell to query and update data as well as perform administrative operations. The mongo shell is a component of the MongoDB distributions. Once you have installed and have started MongoDB, connect the mongo shell to your running MongoDB instance.

### Mongo Shell on Local Linux Instance

You can run mongo shell without any command-line options to connect to a MongoDB instance running on your localhost with default port 27017:

```shell
# log in Mongo Shell without authenticating
mongo

# log in Mongo Shell witt authenticating
mongo admin --username root -p
```

To explicitly specify the port, include the [`--port`](https://docs.mongodb.com/manual/reference/program/mongo/#cmdoption-mongo-port) command-line option. For example, to connect to a MongoDB instance running on localhost with a non-default port 28015:

```shell
mongo --port 28015
```

### Mongo Shell on Local Windows Instance.

Open a terminal window (or a command prompt for Windows) and go to your mongodb installation bin directory:

```shell
cd 
mongo
```
> Adding your `<mongodb installation dir>/bin` to the `PATH` environment variable allows you to type `mongo` instead of having to go to the `<mongodb installation dir>/bin` directory or specify the full path to the binary.


### Useful MongoDB Command

#### #1 show all database, create database, insert data

```shell

> show dbs
admin     0.000GB
config    0.000GB
local     0.000GB

-------------------------

#2 create database test, if there have test, it's means switch to test, example
> use test
switched to db test

# show the current database
> db
test

# show the current database users
> show users

-------------------------

#3 Insert data into the database test, example
> db.test.insert({"name":"company"})
WriteResult({ "nInserted" : 1 })

-------------------------
```


#### #2 Delete the database test, example
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

#### #3 Create administrator user for MongoDB

```
> mongo
> use admin
switched to db admin
> db.createUser( { user: "webs_admin", pwd: "websoft9", roles: ["userAdminAnyDatabase"] } )
Successfully added user: { "user" : "webs_admin", "roles" : [ "userAdminAnyDatabase" ] }


# show the current database users
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