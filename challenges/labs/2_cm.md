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

#start server

```
2019-02-15 10:42:30,177 INFO main:com.cloudera.server.cmf.Main: ================================================================================
2019-02-15 10:42:30,187 INFO main:com.cloudera.server.cmf.Main: Starting SCM Server. JVM Args: [-Dlog4j.configuration=file:/etc/cloudera-scm-server/log4j.properties, -Dfile.encoding=UTF-8, -Dcmf.root.logger=INFO,LOGFILE, -Dcmf.log.dir=/var/log/cloudera-scm-server, -Dcmf.log.file=cloudera-scm-server.log, -Dcmf.jetty.threshhold=WARN, -Dcmf.schema.dir=/usr/share/cmf/schema, -Djava.awt.headless=true, -Djava.net.preferIPv4Stack=true, -Dpython.home=/usr/share/cmf/python, -XX:+UseConcMarkSweepGC, -XX:+UseParNewGC, -XX:+HeapDumpOnOutOfMemoryError, -Xmx2G, -XX:MaxPermSize=256m, -XX:+HeapDumpOnOutOfMemoryError, -XX:HeapDumpPath=/tmp, -XX:OnOutOfMemoryError=kill -9 %p], Args: [], Version: 5.15.2 (#2 built by jenkins on 20181111-0722 git: bb8bf45c81fd454610b53e4945ceb482361f7568)
2019-02-15 10:42:30,256 INFO main:org.mortbay.log: Logging to org.slf4j.impl.Log4jLoggerAdapter(org.mortbay.log) via org.mortbay.log.Slf4jLog
2019-02-15 10:42:30,373 INFO main:org.springframework.context.support.ClassPathXmlApplicationContext: Refreshing org.springframework.context.support.ClassPathXmlApplicationContext@2434cccc: startup date [Fri Feb 15 10:42:30 UTC 2019]; root of context hierarchy

```



## JETTY


```
2019-02-15 10:53:34,163 INFO SearchRepositoryManager-0:com.cloudera.server.web.cmf.search.components.SearchRepositoryManager: Finished constructing repo:2019-02-15T10:53:34.163Z
2019-02-15 10:53:34,566 INFO WebServerImpl:org.mortbay.log: jetty-6.1.26.cloudera.4
2019-02-15 10:53:34,567 INFO WebServerImpl:org.mortbay.log: Started SelectChannelConnector@0.0.0.0:7180
2019-02-15 10:53:34,567 INFO WebServerImpl:com.cloudera.server.cmf.WebServerImpl: Started Jetty server.
2019-02-15 10:53:38,251 INFO ScmActive-0:com.cloudera.server.cmf.components.ScmActive: ScmActive completed successfully.
2019-02-15 10:54:06,966 INFO 444787729@scm-web-5:com.cloudera.server.web.cmf.CMFUserDetailsService: First user 'admin' logging in.
2019-02-15 10:54:07,008 INFO 444787729@scm-web-5:com.cloudera.server.web.cmf.AuthenticationSuccessEventListener: Authentication success for user: 'admin' from 145.131.97.251


``` 


##DB PROP



```

[root@ip-172-32-1-249 /]# cat /etc/cloudera-scm-server/db.properties
# Auto-generated by scm_prepare_database.sh on Fri Feb 15 10:40:30 UTC 2019
#
# For information describing how to configure the Cloudera Manager Server
# to connect to databases, see the "Cloudera Manager Installation Guide."
#
com.cloudera.cmf.db.type=mysql
com.cloudera.cmf.db.host=localhost
com.cloudera.cmf.db.name=scm
com.cloudera.cmf.db.user=scm
com.cloudera.cmf.db.setupType=EXTERNAL
com.cloudera.cmf.db.password=peperonata

```

