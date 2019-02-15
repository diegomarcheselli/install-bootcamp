## DB INTALLED ON ip-172-32-1-249 instead of ip-172-32-1-28



## JDBC

```
  wget https://dev.mysql.com/get/Downloads/Connector-J/mysql-connector-java-5.1.47.tar.gz
```


## DATABASES


```
MariaDB [(none)]> SHOW DATABASES;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| hive               |
| hue                |
| mysql              |
| oozie              |
| performance_schema |
| rman               |
| scm                |
+--------------------+
8 rows in set (0.00 sec)

MariaDB [(none)]>



MariaDB [(none)]> SHOW GRANTS FOR 'scm'@'%';
+----------------------------------------------------------------------------------------------------+
| Grants for scm@%                                                                                   |
+----------------------------------------------------------------------------------------------------+
| GRANT USAGE ON *.* TO 'scm'@'%' IDENTIFIED BY PASSWORD '*B294FD77E512B594F0EA3398DE8C87272B38AF5D' |
| GRANT ALL PRIVILEGES ON `scm`.* TO 'scm'@'%'                                                       |
+----------------------------------------------------------------------------------------------------+
2 rows in set (0.00 sec)

MariaDB [(none)]> SHOW GRANTS FOR 'rman'@'%';
+-----------------------------------------------------------------------------------------------------+
| Grants for rman@%                                                                                   |
+-----------------------------------------------------------------------------------------------------+
| GRANT USAGE ON *.* TO 'rman'@'%' IDENTIFIED BY PASSWORD '*B294FD77E512B594F0EA3398DE8C87272B38AF5D' |
| GRANT ALL PRIVILEGES ON `rman`.* TO 'rman'@'%'                                                      |
+-----------------------------------------------------------------------------------------------------+
2 rows in set (0.00 sec)

MariaDB [(none)]> SHOW GRANTS FOR 'metastore'@'%';
+----------------------------------------------------------------------------------------------------------+
| Grants for metastore@%                                                                                   |
+----------------------------------------------------------------------------------------------------------+
| GRANT USAGE ON *.* TO 'metastore'@'%' IDENTIFIED BY PASSWORD '*B294FD77E512B594F0EA3398DE8C87272B38AF5D' |
| GRANT ALL PRIVILEGES ON `hive`.* TO 'metastore'@'%'                                                      |
+----------------------------------------------------------------------------------------------------------+
2 rows in set (0.00 sec)

MariaDB [(none)]> SHOW GRANTS FOR 'oozie'@'%';
+------------------------------------------------------------------------------------------------------+
| Grants for oozie@%                                                                                   |
+------------------------------------------------------------------------------------------------------+
| GRANT USAGE ON *.* TO 'oozie'@'%' IDENTIFIED BY PASSWORD '*B294FD77E512B594F0EA3398DE8C87272B38AF5D' |
| GRANT ALL PRIVILEGES ON `oozie`.* TO 'oozie'@'%'                                                     |
+------------------------------------------------------------------------------------------------------+
2 rows in set (0.00 sec)

MariaDB [(none)]> SHOW GRANTS FOR 'hue'@'%';
+----------------------------------------------------------------------------------------------------+
| Grants for hue@%                                                                                   |
+----------------------------------------------------------------------------------------------------+
| GRANT USAGE ON *.* TO 'hue'@'%' IDENTIFIED BY PASSWORD '*B294FD77E512B594F0EA3398DE8C87272B38AF5D' |
| GRANT ALL PRIVILEGES ON `hue`.* TO 'hue'@'%'                                                       |
+----------------------------------------------------------------------------------------------------+
2 rows in set (0.00 sec)

```

### hostname


```
[ec2-user@ip-172-32-1-249 ~]$ hostname -f
ip-172-32-1-249

```

## DB VErsion

```
[ec2-user@ip-172-32-1-249 ~]$ mysql -u root -p
Enter password:
Welcome to the MariaDB monitor.  Commands end with ; or \g.
Your MariaDB connection id is 13
Server version: 5.5.60-MariaDB MariaDB Server

Copyright (c) 2000, 2018, Oracle, MariaDB Corporation Ab and others.

```


