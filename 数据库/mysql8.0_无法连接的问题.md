# 无法连接 mysql8.0

MySQL 8.0 版本去除了 password 字段，改用 authentication_string 字段，导致网上可以搜到的各种问题的各种解决方法完全没有效果；同时还更改了加密方式，之前版本的加密方式是「mysql_native_password」，8.0 之后的加密规则更改为「caching_sha2_password 」，这里需要把用户密码加密规则更改为原来的加密方式即可。

```bash
    mysql -u root -p
```


```bash
    # 切换到 mysql 数据库
   use mysql;
   
   # 设置用户密码永不过期
   alter user 'root'@'localhost' identified by 'your pwd' password expire never;
   
   # 用「mysql_native_password」加密方式更新 root 用户密码
   alter user 'root'@'localhost' identified with mysql_native_password by 'your pwd';
   
   # 刷新
   flush privileges;
```

[内容转载来源](https://www.jianshu.com/p/ec35d2e772b8)