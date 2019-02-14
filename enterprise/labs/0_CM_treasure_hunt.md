## What is ubertask optimization?
When MapRedeuce job is submited if ubertask is enabled the ApplicationMaster will run the job in the same JVR


## Where in CM is the Kerberos Security Realm value displayed?
CM->administration -> Security -> kerberos Credentials
the list of principals shows also the Security Realms


## Which CDH service(s) host a property for enabling Kerberos authentication?
HDFS, hove mapred oozie sentry yarn zookeper

## How do you upgrade the CM agents?
using the url:

```
https://CM:7180/cmf/upgrade
```


## Give the tsquery statement used to chart Hue's CPU utilization?
From which roleType?
I.e

```
select cpu_user_rate where roleType=NAMENODE
```
for all namenodes



## Name all the roles that make up the Hive service
. Hive Metastore Server
. WebHCat Server
. HiveServer2 
. Gateway


## What steps must be completed before integrating Cloudera Manager with Kerberos?
xxx
