---
layout: post
title: "play and cloud foundary"
date: 2013-02-28 23:52
comments: true
categories: java
---

## Play! on Cloud Foundary

#### Play!

Install is easy. Now you got verything inatslled.

```
# file conf/application.conf 

db.default.driver=org.postgresql.Driver
db.default.url="jdbc:postgresql://localhost/play_todolist"
db.default.user="username"
db.default.password="password"
```

We are using PostgreSQL.

In thus those two lines is necessary:
`db.default.driver=org.postgresql.Driver` and `db.default.url="jdbc:postgresql://localhost/play_todolist"`

However, you need to download:
[postgresql-9.2-1002.jdbc4.jar](http://jdbc.postgresql.org/download.html)
Note: it's jdbc4, not jdbc3.

##### PostgreSQL

Install is easy for all OSes.

MySQL command -> PostgreSQL command:  

* `mysql -> psql`   
* `show databeses -> \l`
* `show tables -> \d`
* `create database DBNAME -> The same`

For linux

you need to become user `postgres` and then type `psql` to enter the interactive shell.

`\password` could change password
`\password USER` could change password for USER 

To create a user 
`create user USERNAME`

You could figure out the reset using google :)


#### Cloud Foundary

1. Sign up.
2. download rubygem. 
3. deploy

We don't need micro cloud foundary, because we use vagrant (virtualbox).


