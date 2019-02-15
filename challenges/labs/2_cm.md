## INSTALL CLOUDERA MANAGER on ip-172-32-1-28 instead of ip-172-32-1-249



## scm_prepare_database.sh

```
Enter SCM password:
JAVA_HOME=/usr/java/jdk1.7.0_67-cloudera
Verifying that we can write to /etc/cloudera-scm-server
Creating SCM configuration file in /etc/cloudera-scm-server
Executing:  /usr/java/jdk1.7.0_67-cloudera/bin/java -cp :/usr/share/cmf/schema/../lib/* com.cloudera.enterprise.dbutil.DbCommandExecutor /etc/cloudera-scm-server/db.properties com.cloudera.cmf.db.
[                          main] DbCommandExecutor              INFO  Unable to find JDBC driver for database type: MySQL
[                          main] DbCommandExecutor              ERROR JDBC Driver com.mysql.jdbc.Driver not found.
[                          main] DbCommandExecutor              ERROR Exiting with exit code 3
--> Error 3, giving up (use --force if you wish to ignore the error)


```



