## http://ec2-34-247-84-230.eu-west-1.compute.amazonaws.com:7180/api/v14/hosts



```
{
  "items" : [ {
    "hostId" : "6ea3172a-21d1-43c8-931d-2ffbbe88f7fa",
    "ipAddress" : "172.32.1.203",
    "hostname" : "ip-172-32-1-203",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-32-1-249:7180/cmf/hostRedirect/6ea3172a-21d1-43c8-931d-2ffbbe88f7fa",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 16170377216
  }, {
    "hostId" : "40e8f1e6-9911-4dc3-a3c9-93f45af07761",
    "ipAddress" : "172.32.1.214",
    "hostname" : "ip-172-32-1-214",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-32-1-249:7180/cmf/hostRedirect/40e8f1e6-9911-4dc3-a3c9-93f45af07761",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 16170377216
  }, {
    "hostId" : "950d08b5-6e4e-484f-9b65-3193f96666d5",
    "ipAddress" : "172.32.1.236",
    "hostname" : "ip-172-32-1-236",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-32-1-249:7180/cmf/hostRedirect/950d08b5-6e4e-484f-9b65-3193f96666d5",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 16170377216
  }, {
    "hostId" : "0e5be6d5-4231-4fce-9c63-0a350681f5de",
    "ipAddress" : "172.32.1.249",
    "hostname" : "ip-172-32-1-249",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-32-1-249:7180/cmf/hostRedirect/0e5be6d5-4231-4fce-9c63-0a350681f5de",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 16170377216
  }, {
    "hostId" : "0af29e0f-c144-43a2-913b-20afd386e08f",
    "ipAddress" : "172.32.1.28",
    "hostname" : "ip-172-32-1-28",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-32-1-249:7180/cmf/hostRedirect/0af29e0f-c144-43a2-913b-20afd386e08f",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 16170377216
  } ]
}

```

## http://ec2-34-247-84-230.eu-west-1.compute.amazonaws.com:7180/api/v8/clusters/diegomarcheselli/services


```
{
  "items" : [ {
    "name" : "hive",
    "type" : "HIVE",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-172-32-1-249:7180/cmf/serviceRedirect/hive",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "HIVE_HIVEMETASTORES_HEALTHY",
      "summary" : "GOOD"
    }, {
      "name" : "HIVE_HIVESERVER2S_HEALTHY",
      "summary" : "GOOD"
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "Hive"
  }, {
    "name" : "zookeeper",
    "type" : "ZOOKEEPER",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-172-32-1-249:7180/cmf/serviceRedirect/zookeeper",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "ZOOKEEPER_CANARY_HEALTH",
      "summary" : "GOOD"
    }, {
      "name" : "ZOOKEEPER_SERVERS_HEALTHY",
      "summary" : "GOOD"
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "ZooKeeper"
  }, {
    "name" : "hue",
    "type" : "HUE",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-172-32-1-249:7180/cmf/serviceRedirect/hue",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "HUE_HUE_SERVERS_HEALTHY",
      "summary" : "GOOD"
    }, {
      "name" : "HUE_LOAD_BALANCER_HEALTHY",
      "summary" : "GOOD"
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "Hue"
  }, {
    "name" : "oozie",
    "type" : "OOZIE",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-172-32-1-249:7180/cmf/serviceRedirect/oozie",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "OOZIE_OOZIE_SERVERS_HEALTHY",
      "summary" : "GOOD"
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "Oozie"
  }, {
    "name" : "impala",
    "type" : "IMPALA",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-172-32-1-249:7180/cmf/serviceRedirect/impala",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "IMPALA_ASSIGNMENT_LOCALITY",
      "summary" : "DISABLED"
    }, {
      "name" : "IMPALA_CATALOGSERVER_HEALTH",
      "summary" : "GOOD"
    }, {
      "name" : "IMPALA_IMPALADS_HEALTHY",
      "summary" : "GOOD"
    }, {
      "name" : "IMPALA_STATESTORE_HEALTH",
      "summary" : "GOOD"
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "Impala"
  }, {
    "name" : "yarn",
    "type" : "YARN",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-172-32-1-249:7180/cmf/serviceRedirect/yarn",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "YARN_JOBHISTORY_HEALTH",
      "summary" : "GOOD"
    }, {
      "name" : "YARN_NODE_MANAGERS_HEALTHY",
      "summary" : "GOOD"
    }, {
      "name" : "YARN_RESOURCEMANAGERS_HEALTH",
      "summary" : "GOOD"
    }, {
      "name" : "YARN_USAGE_AGGREGATION_HEALTH",
      "summary" : "DISABLED"
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "YARN (MR2 Included)"
  }, {
    "name" : "hdfs",
    "type" : "HDFS",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-172-32-1-249:7180/cmf/serviceRedirect/hdfs",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "HDFS_BLOCKS_WITH_CORRUPT_REPLICAS",
      "summary" : "GOOD"
    }, {
      "name" : "HDFS_CANARY_HEALTH",
      "summary" : "GOOD"
    }, {
      "name" : "HDFS_DATA_NODES_HEALTHY",
      "summary" : "GOOD"
    }, {
      "name" : "HDFS_FREE_SPACE_REMAINING",
      "summary" : "GOOD"
    }, {
      "name" : "HDFS_HA_NAMENODE_HEALTH",
      "summary" : "GOOD"
    }, {
      "name" : "HDFS_MISSING_BLOCKS",
      "summary" : "GOOD"
    }, {
      "name" : "HDFS_UNDER_REPLICATED_BLOCKS",
      "summary" : "GOOD"
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "HDFS"
  } ]
}

```
##rocky 

```

[rocky@ip-172-32-1-249 ~]$ hdfs dfs -ls
Found 1 items
-rw-r--r--   3 rocky rocky          0 2019-02-15 11:45 test.txt

```
 ## denali
 
 #
 ```
[denali@ip-172-32-1-249 ~]$ hdfs dfs -ls
Found 1 items
-rw-r--r--   3 denali denali          0 2019-02-15 11:47 test.txt
[denali@ip-172-32-1-249 ~]$

```
 

## Teragen
not corret paramters 

```
[rocky@ip-172-32-1-249 ~]$ time hadoop jar  /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen      -Ddfs.block.size=32000000      -Dmapred.map.tasks=4      1234000      /user/rocky/teragen/ok
19/02/15 11:58:29 INFO client.RMProxy: Connecting to ResourceManager at ip-172-32-1-203/172.32.1.203:8032
19/02/15 11:58:29 INFO terasort.TeraGen: Generating 1234000 using 4
19/02/15 11:58:29 INFO mapreduce.JobSubmitter: number of splits:4
19/02/15 11:58:29 INFO Configuration.deprecation: mapred.map.tasks is deprecated. Instead, use mapreduce.job.maps
19/02/15 11:58:29 INFO Configuration.deprecation: dfs.block.size is deprecated. Instead, use dfs.blocksize
19/02/15 11:58:29 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1550229133478_0007
19/02/15 11:58:30 INFO impl.YarnClientImpl: Submitted application application_1550229133478_0007
19/02/15 11:58:30 INFO mapreduce.Job: The url to track the job: http://ip-172-32-1-203:8088/proxy/application_1550229133478_0007/
19/02/15 11:58:30 INFO mapreduce.Job: Running job: job_1550229133478_0007
19/02/15 11:58:35 INFO mapreduce.Job: Job job_1550229133478_0007 running in uber mode : false
19/02/15 11:58:35 INFO mapreduce.Job:  map 0% reduce 0%
19/02/15 11:58:41 INFO mapreduce.Job:  map 50% reduce 0%
19/02/15 11:58:43 INFO mapreduce.Job:  map 100% reduce 0%
19/02/15 11:58:43 INFO mapreduce.Job: Job job_1550229133478_0007 completed successfully
19/02/15 11:58:43 INFO mapreduce.Job: Counters: 31
        File System Counters
                FILE: Number of bytes read=0
                FILE: Number of bytes written=596056
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=337
                HDFS: Number of bytes written=123400000
                HDFS: Number of read operations=16
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=8
        Job Counters
                Launched map tasks=4
                Other local map tasks=4
                Total time spent by all maps in occupied slots (ms)=16946
                Total time spent by all reduces in occupied slots (ms)=0
                Total time spent by all map tasks (ms)=16946
                Total vcore-milliseconds taken by all map tasks=16946
                Total megabyte-milliseconds taken by all map tasks=17352704
        Map-Reduce Framework
                Map input records=1234000
                Map output records=1234000
                Input split bytes=337
                Spilled Records=0
                Failed Shuffles=0
                Merged Map outputs=0
                GC time elapsed (ms)=249
                CPU time spent (ms)=5640
                Physical memory (bytes) snapshot=980594688
                Virtual memory (bytes) snapshot=6321086464
                Total committed heap usage (bytes)=1349517312
        org.apache.hadoop.examples.terasort.TeraGen$Counters
                CHECKSUM=2652127169120142
        File Input Format Counters
                Bytes Read=0
        File Output Format Counters
                Bytes Written=123400000

real    0m16.180s
user    0m4.227s
sys     0m0.229s

``` 

