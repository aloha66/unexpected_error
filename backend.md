1. mysql8.0 Navicat连接报错
Client does not support authentication protocol requested by server; consider upgrading MySQL client。
解决方案：
```
USE mysql;
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY '你的密码';
FLUSH PRIVILEGES;
```



## mongodb
@5.2.8之后

1. 消除部分警告`collection.ensureIndex is deprecated` 
[解决方案](https://stackoverflow.com/questions/51960171/node63208-deprecationwarning-collection-ensureindex-is-deprecated-use-creat)
```
mongoose.set('useNewUrlParser', true);
mongoose.set('useFindAndModify', false);
mongoose.set('useCreateIndex', true);
```
