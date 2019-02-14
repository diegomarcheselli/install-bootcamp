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
* Hive Metastore Server
* WebHCat Server
* HiveServer2 
* Gateway


## What steps must be completed before integrating Cloudera Manager with Kerberos?

### Step 1:
To install packages for a Kerberos server:


### Step 2:
modify /var/kerberos/krb5kdc/kdc.conf

### Step 3:
modify /etc/krb5.conf 

### Step 4:
Create KDC database


### Step 5:
add cloudera-scm principal,


### Step 6:
Add */admin and cloudera-scm to ACL


### Step 7:
Adds the password policy to the database.


### Step 8:
do not generate the cmf.keytab make CM generate it for us in the web UI


### Step 9:
Move keytab file to cloudera-scm-server location and provide appropriate permissions.


### Step 10:
Create a file called cmf.principal for cloudera-scm


### Step 11:
Start Kerberos kdc and admin uxxx
