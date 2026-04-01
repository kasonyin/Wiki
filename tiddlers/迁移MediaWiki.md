## 备份数据库
以 MySQL 数据为例：
```
mysqldump --no-tablespaces -h localhost -u 用户名 -p'密码' --default-character-set=utf8 表名 > backup.sql
```
* 某些较新版本的 MySQL (比如8.0)可能会显示有关表空间和 PROCESS 权限的错误。MediaWiki 不使用表空间。使用`--no-tablespaces` 解决
* -p后要紧跟密码
可以使用gizp来生成更小的文件：
```
mysqldump --no-tablespaces -h localhost -u 用户名 -p'密码' --default-character-set=utf8 表名 | gzip > backup.sql
```
## 备份文件系统
* 在创建备份前，建议将维基设置为只读模式
在 Localhost.php 中增加：
```
$wgReadOnly = '提示内容';
```
* 备份文件夹
```
tar -czf wiki.tar.gz /var/www/wiki
```

<<reuse-tiddler "安装MediaWiki">>