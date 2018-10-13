## Install Sequelize

Untuk memakai sequelize, Anda harus masuk terlebih dahulu ke folder proyek Anda dan melakukan beberapa instalasi sebagai berikut:

```
npm init
npm install --save sequelize sequelize-cli sqlite3
```

### Init sequielize dalam proyek

Lakukan init sequelize agar mendapatkan folder pengelolaan database yang telah disediakan oleh sequelize seperti berikut ini.
```
sequelize init
```

![Sequelize Init](https://github.com/talkasrul/workshop-sequelize/blob/master/img/sequelizeInit.png?raw=true)

Setelah melakukan init sequelize lakukan sedikit configurasi pada file `config.json`, seperti berikut.

```
{
  "development": {
    "dialect": "sqlite",
    "storage": "./database.sqlite3"
  },
  "test": {
    "username": "root",
    "password": null,
    "database": "database_test",
    "host": "127.0.0.1",
    "dialect": "mysql"
  },
  "production": {
    "username": "root",
    "password": null,
    "database": "database_production",
    "host": "127.0.0.1",
    "dialect": "mysql"
  }
}
```

### [Model Generate >>>>](https://github.com/talkasrul/workshop-sequelize/blob/master/learn/02-model-generate.md)