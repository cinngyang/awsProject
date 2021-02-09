[Ubuntu 架設 MySQL](https://magiclen.org/ubuntu-server-mysql-php/)
+ MySQL伺服器的設定
檔路徑為/etc/mysql/mysql.conf.d/mysqld.cnf<br>

+ Python 安裝<br>
sudo pip3 install mysql-connector

import pymysql
import 


<pre><code>sudo netstat -tlnp | grep mysqld)
mysqld --validate-config
sudo systemctl restart mysql
</code><pre>

+ Commnad

<pre><code>
SHOW DATABASES;
CREATE DATABASE `dbname`;
USE `dbname`;
SHOW TABLES;

CREATE USER 'dbuser'@'localhost' IDENTIFIED BY 'PWD';
GRANT ALL ON `dbname`.* TO 'dbuser'@'localhost';

CREATE TABLE `users` (
    `userid` tinyint SIGNED NOT NULL PRIMARY KEY AUTO_INCREMENT,
    `username` varchar(50)
);


</code><pre>
