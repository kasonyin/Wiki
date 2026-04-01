## 构建数据库
### 登录数据库
```
mysql -u root -p
```
如果数据库没有设置root用户，直接以`sudo mysql`登录
### 创建数据库
```
CREATE DATABASE mediawikidb;
```
### 创建用户
```
CREATE USER  mediawiki@localhost IDENTIFIED BY '密码';  
```
### 赋予权限
```
GRANT ALL ON mediawikidb.* TO mediawiki@localhost WITH GRANT OPTION;
FLUSH PRIVILEGES;
```

## 下载安装MediaWiki
