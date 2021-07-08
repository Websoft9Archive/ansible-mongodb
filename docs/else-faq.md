# FAQ

#### What is the password for the database root user?

The password is stored in the server related file: `/credentials/password.txt`

#### Is there a web-base GUI database management tools?

Yes, adminMongo is on it, visit by *http://Server Internet IP:9091*

#### Can I connect MongoDB from Internet(remote)?

You should [enable the remote connection](/solution-more.md#enable-the-mongodb-remote-connection) first

#### What are the Client and Server of MongoDB?

MongoDB Server refers to the MongoDB program ontology, and MongoDB Client refers to the client that uses TCP protocol to connect to the program local. They are two completely different programs, which means that they do not need to be installed on the same service at the same time.

#### What's difference between command **mongod** and **mongo**?

* mongod is the command for start MongoDB server's service  
* mongo is MongoDB shell  

#### MongoDB Community vs MongoDB Enterprise？

MongoDB Community is the source available and free to use edition of MongoDB.  
MongoDB Enterprise is available as part of the MongoDB Enterprise Advanced subscription and includes comprehensive support for your MongoDB deployment.   MongoDB Enterprise also adds enterprise-focused features such as LDAP and Kerberos support, on-disk encryption, and auditing.  

#### Could I directly access mongodb without authentication?

Yes, MongoDB does not enable access control during installation by default. So it can be accessed without mongodb user name and password, e.g. through this URL：mongodb://localhost/admin.
 > MongoDB [Enable Access Control](https://docs.mongodb.com/manual/tutorial/enable-authentication/)

#### What is the **admin** database of MongoDB?

The MongoDB installation will include an **admin** database by default. If you create an administrator account, you must store it in this admin

#### Which authentication MongoDB support?

MongoDB provides various features, such as authentication, access control, encryption, to secure your MongoDB deployments. Some key security features include:

| Authentication | Authorization | TLS/SSL | Enterprise Only |
| :--- | :--- | :--- | :--- |
| [Authentication](https://docs.mongodb.com/manual/core/authentication/)<br />[SCRAM](https://docs.mongodb.com/manual/core/security-scram/)<br />[x.509](https://docs.mongodb.com/manual/core/security-x.509/) | [Role-Based Access Control](https://docs.mongodb.com/manual/core/authorization/)<br />[Enable Auth](https://docs.mongodb.com/manual/tutorial/enable-authentication/)<br />[Manage Users and Roles](https://docs.mongodb.com/manual/tutorial/manage-users-and-roles/) | [TLS/SSL (Transport Encryption)](https://docs.mongodb.com/manual/core/security-transport-encryption/)<br />[Configure mongod and mongos for TLS/SSL](https://docs.mongodb.com/manual/tutorial/configure-ssl/)<br />[TLS/SSL Configuration for Clients](https://docs.mongodb.com/manual/tutorial/configure-ssl-clients/) | [Kerberos Authentication](https://docs.mongodb.com/manual/core/kerberos/)<br />[LDAP Proxy Authentication](https://docs.mongodb.com/manual/core/security-ldap/)<br />[Encryption at Rest](https://docs.mongodb.com/manual/core/security-encryption-at-rest/)<br />[Auditing](https://docs.mongodb.com/manual/core/auditing/) |

> MongoDB also provides the [Security Checklist](https://docs.mongodb.com/manual/administration/security-checklist/) for a list of recommended actions to protect a MongoDB deployment.

#### What platforms does MongoDB support?
For the list of supported platforms, see [Supported Platforms](https://docs.mongodb.com/manual/administration/production-notes/#prod-notes-supported-platforms).

#### How to get the status of MongoDB?

Run command to list mongodb process
```
ps -ef| grep mongod
```
#### Can I modify the data directory of MongoDB?

Yes, modify the /etc/mongod.conf

#### What's the difference between Deployment and Installation?

- Deployment is a process of installing and configuring a sequence of software in sequence in a different order, which is a complex system engineering.  
- Installation is the process of starting the initial wizard after the application is prepared.  
- Installation is simpler than deployment. 

#### What's Cloud Platform?

Cloud platform refers to platform manufacturers that provide cloud computing services, such as: **Azure, AWS, Alibaba Cloud, HUAWEI CLOUD, Tencent Cloud**, etc.

#### What is the difference between Instance, Cloud Server, Virtual Machine, ECS, EC2, CVM, and VM?

No difference, just the terminology used by different manufacturers, actually cloud servers