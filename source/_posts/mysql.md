---
title: mysql 8
date: 2023-06-09 23:42:34
tags:
---

# MySQL 8

## 修改密码

**MySql 从8.0**开始修改密码有了变化，在user表加了字段authentication_string，修改密码前先检查authentication_string是否为空

+ 如果不为空
   ```sql
   use mysql; 
    
   update user set authentication_string='' where user='root';--将字段置为空
    
   ALTER user 'root'@'localhost' IDENTIFIED BY 'root';--修改密码为root
   ```
+ 如果为空直接修改
   ```sql
   ALTER user 'root'@'localhost' IDENTIFIED BY 'newpassword';
   ```





## 设置MySQL远程登陆

1. 以root用户登录MySQL

2. 输入语句，进入mysql数据库：

   ```
   use mysql
   ```

   

3. 查询当前用户的Host属性

   ```
   select User, Host from user;
   ```

   

4. 更新域属性，‘%’ 表示允许任意ip地址访问：

   ```
   update user set host='%' where user ='root';
   ```

   

5. 后执行：

   ```
   FLUSH PRIVILEGES;
   ```

   

6. 再执行授权语句：

   ```
   GRANT ALL PRIVILEGES ON *.* TO 'root'@'%' WITH GRANT OPTION;
   ```

   

## 用户
增加用户

```sql
CREATE USER 'username'@'host' IDENTIFIED BY 'password';
```

赋予权限

```sql
GRANT ALL PRIVILEGES ON *.* TO 'username'@'host';
```



删除用户

```sql
DROP USER 'username'@'host';
```



## 数据库

```
create database <database_name>;
drop database <database_name>;
show databases;
```

