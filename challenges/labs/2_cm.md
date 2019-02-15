## INSTALL CLOUDERA MANAGER on ip-172-32-1-28 instead of ip-172-32-1-249



## scm_prepare_database.sh

```
[root@ip-172-32-1-249 ec2-user]# /usr/share/cmf/schema/scm_prepare_database.sh mysql scm scm                                                          Enter SCM password:
JAVA_HOME=/usr/java/jdk1.7.0_67-cloudera
Verifying that we can write to /etc/cloudera-scm-server
Creating SCM configuration file in /etc/cloudera-scm-server
Executing:  /usr/java/jdk1.7.0_67-cloudera/bin/java -cp /usr/share/java/mysql-connector-java.jar:/usr/share/cmf/schema/../lib/* com.cloudera.enterprise.dbutil.DbCommandExecutor /etc/cloudera-scm-server/db.properties com.cloudera.cmf.db.
[                          main] DbCommandExecutor              INFO  Successfully connected to database.
All done, your SCM database is configured correctly!


```



