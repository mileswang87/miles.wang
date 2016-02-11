---
title: bookshelf.js和express
date: 2016-02-10 23:52:55
tags:
    - bookshelf.js
    - express
    - nodejs
---

### 1. 安装dependencies
```
$ npm install knex --save
$ npm install bookshelf --save

# Then add one of the following:
$ npm install pg
$ npm install mysql
$ npm install mariasql
$ npm install sqlite3
```

### 2. 建立models/index.js
```
var knex = require('knex')({
  client: 'mysql',
  connection: {
    host     : '127.0.0.1',
    user     : 'your_database_user',
    password : 'your_database_password',
    database : 'myapp_test',
    charset  : 'utf8'
  }
});

var bookshelf = require('bookshelf')(knex);

var User = bookshelf.Model.extend({
  tableName: 'users'
});
```

TODO