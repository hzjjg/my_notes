# mysql 安装与最基本配置

[官网](https://www.mysql.com/)  
[官网文档](https://dev.mysql.com/doc/refman/8.0/en/)

安装参考： (博客地址)[https://www.jianshu.com/p/4cb5ef29a099]

## 安装环境

操作系统：macOS mojave 10.14

安装
```shell
    $ brew install mysql
```

启动mysql 服务
```shell
    $ mysql.server start
```

基本配置
```shell
    $ mysql_secure_installation
```

配置过程中会有几个命令交互，一步步走下去就好了  
*  提示是否设置密码
*  提示选择密码强度等级
*  按照所选的密码强度要求设定密码
*  提示密码强度100,符合要求继续进行
*  提示删除默认无密码用户
*  提示禁止远程root登录
*  提示删除默认自带的test数据库
*  提示是否重新加载privilege tables

All done !

测试登录
```
    $ mysql -u root -p
```

登录成功