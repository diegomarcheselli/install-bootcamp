## STATUS of HIVE


```
curl  -u  diegomarcheselli:cloudera 'ip-172-32-1-224:7180/api/v2/clusters/diegomarcheselli/services/hive'
{
  "name" : "hive",
  "type" : "HIVE",
  "clusterRef" : {
    "clusterName" : "cluster"
  },
  "serviceUrl" : "http://ip-172-32-1-224:7180/cmf/serviceRedirect/hive",
  "serviceState" : "STARTED",
  "healthSummary" : "GOOD",
  "healthChecks" : [ {
    "name" : "HIVE_HIVEMETASTORES_HEALTHY",
    "summary" : "GOOD"
  }, {
    "name" : "HIVE_HIVESERVER2S_HEALTHY",
    "summary" : "GOOD"
  } ],
  "configStale" : false,
  "maintenanceMode" : false,
  "maintenanceOwners" : [ ],
  "displayName" : "Hive"
}

```


## STOP of HIVE


```
curl -XPOST -u  diegomarcheselli:cloudera 'ip-172-32-1-224:7180/api/v2/clusters/diegomarcheselli/services/hive/commands/stop'
{
  "id" : 1593,
  "name" : "Stop",
  "startTime" : "2019-02-14T14:58:53.363Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
  
  
  ------------------------------------
  
  
 curl  -u  diegomarcheselli:cloudera 'ip-172-32-1-224:7180/api/v2/clusters/diegomarcheselli/services/hive'     {
  "name" : "hive",
  "type" : "HIVE",
  "clusterRef" : {
    "clusterName" : "cluster"
  },
  "serviceUrl" : "http://ip-172-32-1-224:7180/cmf/serviceRedirect/hive",
  "serviceState" : "STOPPED",
  "healthSummary" : "DISABLED",
  "healthChecks" : [ {
    "name" : "HIVE_HIVEMETASTORES_HEALTHY",
    "summary" : "DISABLED"
  }, {
    "name" : "HIVE_HIVESERVER2S_HEALTHY",
    "summary" : "DISABLED"
  } ],
  "configStale" : false,
  "maintenanceMode" : false,
  "maintenanceOwners" : [ ],
  "displayName" : "Hive"
}
```


## START of HIVE


```
  curl -XPOST -u  diegomarcheselli:cloudera 'ip-172-32-1-224:7180/api/v2/clusters/diegomarcheselli/services/hive/commands/start'
{
  "id" : 1599,
  "name" : "Start",
  "startTime" : "2019-02-14T14:59:54.209Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}[

---------------------------


curl -u  diegomarcheselli:cloudera 'ip-172-32-1-224:7180/api/v2/clusters/diegomarcheselli/services/hive'     {
  "name" : "hive",
  "type" : "HIVE",
  "clusterRef" : {
    "clusterName" : "cluster"
  },
  "serviceUrl" : "http://ip-172-32-1-224:7180/cmf/serviceRedirect/hive",
  "serviceState" : "STARTING",
  "healthSummary" : "DISABLED",
  "healthChecks" : [ {
    "name" : "HIVE_HIVEMETASTORES_HEALTHY",
    "summary" : "DISABLED"
  }, {
    "name" : "HIVE_HIVESERVER2S_HEALTHY",
    "summary" : "DISABLED"
  } ],
  "configStale" : false,
  "maintenanceMode" : false,
  "maintenanceOwners" : [ ],
  "displayName" : "Hive"
}
```



