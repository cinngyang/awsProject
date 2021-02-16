[TOC]

##安裝 MySQL

```shell
sudo apt-get install mysql-server
sudo apt-get install mysql-client
```

+ 檔路徑為/etc/mysql/mysql.conf.d/mysqld.cnf<br>確認 mysql 狀態<br>設定root 密碼<br>安裝安全性套件<br>

  ```shell
service mysql status
sudo mysql -u root -p
sudo mysql_secure_installation
  ```

+ 檢查 mysql 狀態

  ```shell
  sudo netstat -tlnp | grep mysqld
  mysqld --validate-config
  service mysql restart
  sudo systemctl restart mysql
  sudo -u root #登入 mysql
  ```
  
##建立新使用者

建立使用者,賦予資料庫權限&重新載入權限表

  ```shell
  show databases;
  show tables;
  CREATE USER 'WebUser'@'localhost' IDENTIFIED BY 'XXXXXXX';
  GRANT ALL PRIVILEGES ON *.* TO 'WebUser'@'localhost';
  FLUSH PRIVILEGES;
  ```

##建立資料庫

```shell
CREATE DATABASE `dbname`;
USE `dbname`;
SHOW TABLES;
CREATE USER 'dbuser'@'localhost' IDENTIFIED BY 'PWD';
GRANT ALL ON `dbname`.* TO 'dbuser'@'localhost';

CREATE TABLE `users` (
    `userid` tinyint SIGNED NOT NULL PRIMARY KEY AUTO_INCREMENT,
    `username` varchar(50)
);

```

##常用命令
檢視 columns

```shell
SELECT * FROM `users`;
DESCRIBE yourDatabasename.yourTableName;
SHOW COLUMNS FROM my_table;
```



##Python 使用mysql
sudo pip3 install mysql-connector
pip3 install pymysql


------

[Ubuntu 架設 MySQL](https://magiclen.org/ubuntu-server-mysql-php/)
[python mysql](https://www.itread01.com/content/1544933702.html)

