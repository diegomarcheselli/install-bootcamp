
```
{
  "timestamp" : "2019-02-14T14:18:04.883Z",
  "clusters" : [ {
    "name" : "diegomarcheselli",
    "version" : "CDH5",
    "services" : [ {
      "name" : "hive",
      "type" : "HIVE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "HIVEMETASTORE",
          "items" : [ {
            "name" : "hive_enable_db_notification",
            "value" : "true"
          }, {
            "name" : "hive_metastore_java_heapsize",
            "value" : "617611264"
          } ]
        }, {
          "roleType" : "HIVESERVER2",
          "items" : [ {
            "name" : "hiveserver2_enable_impersonation",
            "value" : "false"
          }, {
            "name" : "hiveserver2_java_heapsize",
            "value" : "617611264"
          }, {
            "name" : "hiveserver2_spark_driver_memory",
            "value" : "966367641"
          }, {
            "name" : "hiveserver2_spark_executor_cores",
            "value" : "4"
          }, {
            "name" : "hiveserver2_spark_executor_memory",
            "value" : "3785306931"
          }, {
            "name" : "hiveserver2_spark_yarn_driver_memory_overhead",
            "value" : "102"
          }, {
            "name" : "hiveserver2_spark_yarn_executor_memory_overhead",
            "value" : "637"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_metastore_database_host",
          "value" : "172.32.1.224"
        }, {
          "name" : "hive_metastore_database_password",
          "value" : "peperonata"
        }, {
          "name" : "hive_metastore_database_user",
          "value" : "metastore"
        }, {
          "name" : "hive_proxy_user_groups_list",
          "value" : "hive,hue,sentry"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "sentry_service",
          "value" : "sentry"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hive-GATEWAY-3ee73173aa3523d37af280d911049cbb",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "6afe0ad9-1a08-4457-bb9e-b5a39852e858"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-5c2f3a655b58c63006647066e3f7f66d",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "5ad6242b-46df-4569-87a1-13f589e0ac39"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-7f375ac390d81812fd5fbd4b0a4c5bbd",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "d52e9214-b778-4f8e-85fd-f4139b7b15ed"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-861c1fad29b3b665b36fc9aa470c7eac",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "70f9859e-3adf-44a0-983f-5c683318ac36"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-99d29bc2fc4fa02e8e4b3f221bc9a101",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "a31c80ba-69df-49a3-abbf-707c10480e12"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-HIVEMETASTORE-3ee73173aa3523d37af280d911049cbb",
        "type" : "HIVEMETASTORE",
        "hostRef" : {
          "hostId" : "6afe0ad9-1a08-4457-bb9e-b5a39852e858"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "675kwkymu3gaw380tz6z243iy"
          } ]
        }
      }, {
        "name" : "hive-HIVESERVER2-3ee73173aa3523d37af280d911049cbb",
        "type" : "HIVESERVER2",
        "hostRef" : {
          "hostId" : "6afe0ad9-1a08-4457-bb9e-b5a39852e858"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "6ma9h34wten0n39xelm2v1x42"
          } ]
        }
      } ],
      "displayName" : "Hive"
    }, {
      "name" : "zookeeper",
      "type" : "ZOOKEEPER",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "SERVER",
          "items" : [ {
            "name" : "zookeeper_server_java_heapsize",
            "value" : "617611264"
          } ]
        } ],
        "items" : [ {
          "name" : "enableSecurity",
          "value" : "true"
        } ]
      },
      "roles" : [ {
        "name" : "zookeeper-SERVER-3ee73173aa3523d37af280d911049cbb",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "6afe0ad9-1a08-4457-bb9e-b5a39852e858"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "4mwcgi7u520owfn6ugtohv260"
          }, {
            "name" : "serverId",
            "value" : "3"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-5c2f3a655b58c63006647066e3f7f66d",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "5ad6242b-46df-4569-87a1-13f589e0ac39"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "7uhvhxqmt0l9awnjs2xj2konf"
          }, {
            "name" : "serverId",
            "value" : "2"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-861c1fad29b3b665b36fc9aa470c7eac",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "70f9859e-3adf-44a0-983f-5c683318ac36"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "dvaj39av1vu88p3fdjp1j5dgw"
          }, {
            "name" : "serverId",
            "value" : "1"
          } ]
        }
      } ],
      "displayName" : "ZooKeeper"
    }, {
      "name" : "hue",
      "type" : "HUE",
      "config" : {
        "roleTypeConfigs" : [ ],
        "items" : [ {
          "name" : "database_host",
          "value" : "172.32.1.224"
        }, {
          "name" : "database_password",
          "value" : "peperonata"
        }, {
          "name" : "database_type",
          "value" : "mysql"
        }, {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "hue_webhdfs",
          "value" : "hdfs-HTTPFS-3ee73173aa3523d37af280d911049cbb"
        }, {
          "name" : "oozie_service",
          "value" : "oozie"
        }, {
          "name" : "sentry_service",
          "value" : "sentry"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hue-HUE_LOAD_BALANCER-3ee73173aa3523d37af280d911049cbb",
        "type" : "HUE_LOAD_BALANCER",
        "hostRef" : {
          "hostId" : "6afe0ad9-1a08-4457-bb9e-b5a39852e858"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9ep9qv741wahcmqt9w8hbhf93"
          } ]
        }
      }, {
        "name" : "hue-HUE_SERVER-3ee73173aa3523d37af280d911049cbb",
        "type" : "HUE_SERVER",
        "hostRef" : {
          "hostId" : "6afe0ad9-1a08-4457-bb9e-b5a39852e858"
        },
        "config" : {
          "items" : [ {
            "name" : "navmetadataserver_cmdb_password",
            "value" : "cb02ae15-b65b-4a7e-9e25-30dfa267cccb"
          }, {
            "name" : "role_jceks_password",
            "value" : "3si5n23ll7ipa2z7swmbtz43d"
          }, {
            "name" : "secret_key",
            "value" : "S7P9SbPcwl2R1msUkSH3rBysberfvG"
          } ]
        }
      }, {
        "name" : "hue-KT_RENEWER-3ee73173aa3523d37af280d911049cbb",
        "type" : "KT_RENEWER",
        "hostRef" : {
          "hostId" : "6afe0ad9-1a08-4457-bb9e-b5a39852e858"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "eqitie0n9lyq79wthlpmprx1b"
          } ]
        }
      } ],
      "displayName" : "Hue"
    }, {
      "name" : "oozie",
      "type" : "OOZIE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "OOZIE_SERVER",
          "items" : [ {
            "name" : "oozie_database_host",
            "value" : "172.32.1.224"
          }, {
            "name" : "oozie_database_password",
            "value" : "peperonata"
          }, {
            "name" : "oozie_database_type",
            "value" : "mysql"
          }, {
            "name" : "oozie_database_user",
            "value" : "oozie"
          }, {
            "name" : "oozie_java_heapsize",
            "value" : "617611264"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "oozie-OOZIE_SERVER-3ee73173aa3523d37af280d911049cbb",
        "type" : "OOZIE_SERVER",
        "hostRef" : {
          "hostId" : "6afe0ad9-1a08-4457-bb9e-b5a39852e858"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "8qw7wa7hqroq856jdlt53rb7k"
          } ]
        }
      } ],
      "displayName" : "Oozie"
    }, {
      "name" : "yarn",
      "type" : "YARN",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "GATEWAY",
          "items" : [ {
            "name" : "mapred_reduce_tasks",
            "value" : "8"
          }, {
            "name" : "mapred_submit_replication",
            "value" : "3"
          } ]
        }, {
          "roleType" : "JOBHISTORY",
          "items" : [ {
            "name" : "mr2_jobhistory_java_heapsize",
            "value" : "617611264"
          } ]
        }, {
          "roleType" : "NODEMANAGER",
          "items" : [ {
            "name" : "yarn_nodemanager_heartbeat_interval_ms",
            "value" : "100"
          }, {
            "name" : "yarn_nodemanager_local_dirs",
            "value" : "/yarn/nm"
          }, {
            "name" : "yarn_nodemanager_log_dirs",
            "value" : "/yarn/container-logs"
          }, {
            "name" : "yarn_nodemanager_resource_cpu_vcores",
            "value" : "4"
          }, {
            "name" : "yarn_nodemanager_resource_memory_mb",
            "value" : "4913"
          } ]
        }, {
          "roleType" : "RESOURCEMANAGER",
          "items" : [ {
            "name" : "resource_manager_java_heapsize",
            "value" : "617611264"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_mb",
            "value" : "4913"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_vcores",
            "value" : "3"
          } ]
        } ],
        "items" : [ {
          "name" : "hdfs_service",
          "value" : "hdfs"
        }, {
          "name" : "rm_dirty",
          "value" : "false"
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "80"
        }, {
          "name" : "yarn_service_cgroups",
          "value" : "false"
        }, {
          "name" : "yarn_service_lce_always",
          "value" : "false"
        }, {
          "name" : "zk_authorization_secret_key",
          "value" : "KYlGTpT1aUXSwe28ld4NxAq9DkBdPZ"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "yarn-JOBHISTORY-3ee73173aa3523d37af280d911049cbb",
        "type" : "JOBHISTORY",
        "hostRef" : {
          "hostId" : "6afe0ad9-1a08-4457-bb9e-b5a39852e858"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "e9e93gdmg6bk1ysda8en5p6um"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-5c2f3a655b58c63006647066e3f7f66d",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "5ad6242b-46df-4569-87a1-13f589e0ac39"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "3p4lo17oe46tgilx6nyb36djz"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-7f375ac390d81812fd5fbd4b0a4c5bbd",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "d52e9214-b778-4f8e-85fd-f4139b7b15ed"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "wgzl3jhr9nbs5lidibreco9r"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-861c1fad29b3b665b36fc9aa470c7eac",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "70f9859e-3adf-44a0-983f-5c683318ac36"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "50w7slrhy76os1wix9abgnb1w"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-99d29bc2fc4fa02e8e4b3f221bc9a101",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "a31c80ba-69df-49a3-abbf-707c10480e12"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "di4w0z26qvgfafeoqn2p95rbs"
          } ]
        }
      }, {
        "name" : "yarn-RESOURCEMANAGER-3ee73173aa3523d37af280d911049cbb",
        "type" : "RESOURCEMANAGER",
        "hostRef" : {
          "hostId" : "6afe0ad9-1a08-4457-bb9e-b5a39852e858"
        },
        "config" : {
          "items" : [ {
            "name" : "rm_id",
            "value" : "55"
          }, {
            "name" : "role_jceks_password",
            "value" : "52eqyncn35uqgcpb9ocr3lmj8"
          } ]
        }
      } ],
      "displayName" : "YARN (MR2 Included)"
    }, {
      "name" : "hdfs",
      "type" : "HDFS",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "BALANCER",
          "items" : [ {
            "name" : "balancer_java_heapsize",
            "value" : "617611264"
          } ]
        }, {
          "roleType" : "DATANODE",
          "items" : [ {
            "name" : "datanode_java_heapsize",
            "value" : "1073741824"
          }, {
            "name" : "dfs_data_dir_list",
            "value" : "/dfs/dn"
          }, {
            "name" : "dfs_datanode_data_dir_perm",
            "value" : "700"
          }, {
            "name" : "dfs_datanode_du_reserved",
            "value" : "5367448780"
          }, {
            "name" : "dfs_datanode_http_port",
            "value" : "1006"
          }, {
            "name" : "dfs_datanode_max_locked_memory",
            "value" : "4294967296"
          }, {
            "name" : "dfs_datanode_port",
            "value" : "1004"
          }, {
            "name" : "rm_cpu_shares",
            "value" : "400"
          }, {
            "name" : "rm_io_weight",
            "value" : "200"
          } ]
        }, {
          "roleType" : "GATEWAY",
          "items" : [ {
            "name" : "dfs_client_use_trash",
            "value" : "true"
          } ]
        }, {
          "roleType" : "JOURNALNODE",
          "items" : [ {
            "name" : "dfs_journalnode_edits_dir",
            "value" : "/data/1/journal"
          } ]
        }, {
          "roleType" : "NAMENODE",
          "items" : [ {
            "name" : "dfs_name_dir_list",
            "value" : "/dfs/nn"
          }, {
            "name" : "dfs_namenode_servicerpc_address",
            "value" : "8022"
          } ]
        }, {
          "roleType" : "SECONDARYNAMENODE",
          "items" : [ {
            "name" : "fs_checkpoint_dir_list",
            "value" : "/dfs/snn"
          } ]
        } ],
        "items" : [ {
          "name" : "dfs_encrypt_data_transfer_algorithm",
          "value" : "AES/CTR/NoPadding"
        }, {
          "name" : "dfs_ha_fencing_cloudera_manager_secret_key",
          "value" : "UXuGUvWdtLZLSwXtTE4XGxxbiW0NgQ"
        }, {
          "name" : "fc_authorization_secret_key",
          "value" : "wKA2Ob5NfmBa2K9rXudntZE25XQWqF"
        }, {
          "name" : "hadoop_security_authentication",
          "value" : "kerberos"
        }, {
          "name" : "hadoop_security_authorization",
          "value" : "true"
        }, {
          "name" : "http_auth_signature_secret",
          "value" : "g7sPQtgnoPYBXQTIH91bgCvAqLWnM2"
        }, {
          "name" : "rm_dirty",
          "value" : "false"
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "20"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hdfs-BALANCER-3ee73173aa3523d37af280d911049cbb",
        "type" : "BALANCER",
        "hostRef" : {
          "hostId" : "6afe0ad9-1a08-4457-bb9e-b5a39852e858"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-DATANODE-5c2f3a655b58c63006647066e3f7f66d",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "5ad6242b-46df-4569-87a1-13f589e0ac39"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "6dvo853b23yp1qzxrbo7znkbf"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-7f375ac390d81812fd5fbd4b0a4c5bbd",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "d52e9214-b778-4f8e-85fd-f4139b7b15ed"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "6oixk7q88qnk3qrbgtyz6wbzq"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-861c1fad29b3b665b36fc9aa470c7eac",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "70f9859e-3adf-44a0-983f-5c683318ac36"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "7z9b1zge1ls9ajndu5b5frw10"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-99d29bc2fc4fa02e8e4b3f221bc9a101",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "a31c80ba-69df-49a3-abbf-707c10480e12"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "a1w2cuco75hd2b18y5cntyo7w"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-3ee73173aa3523d37af280d911049cbb",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "6afe0ad9-1a08-4457-bb9e-b5a39852e858"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "6i378tt9udrhpohwlr52feci8"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-5c2f3a655b58c63006647066e3f7f66d",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "5ad6242b-46df-4569-87a1-13f589e0ac39"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "3hotnft0s6zctylzz9pud7zhu"
          } ]
        }
      }, {
        "name" : "hdfs-HTTPFS-3ee73173aa3523d37af280d911049cbb",
        "type" : "HTTPFS",
        "hostRef" : {
          "hostId" : "6afe0ad9-1a08-4457-bb9e-b5a39852e858"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "dntp1wlvv68kvxmeiqerozm7i"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-7f375ac390d81812fd5fbd4b0a4c5bbd",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "d52e9214-b778-4f8e-85fd-f4139b7b15ed"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "4vqrkqr1ohf07l6vvtw97mef9"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-861c1fad29b3b665b36fc9aa470c7eac",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "70f9859e-3adf-44a0-983f-5c683318ac36"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "jlquqe1dw455l1x9w6kfy6gd"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-99d29bc2fc4fa02e8e4b3f221bc9a101",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "a31c80ba-69df-49a3-abbf-707c10480e12"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "1x7l7zyuqoifg35puf0297x6z"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-3ee73173aa3523d37af280d911049cbb",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "6afe0ad9-1a08-4457-bb9e-b5a39852e858"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "nameservice1"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "nameservice1"
          }, {
            "name" : "namenode_id",
            "value" : "57"
          }, {
            "name" : "role_jceks_password",
            "value" : "96wwh9o9rymxvmsfuyt1o6ipn"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-5c2f3a655b58c63006647066e3f7f66d",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "5ad6242b-46df-4569-87a1-13f589e0ac39"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "nameservice1"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "nameservice1"
          }, {
            "name" : "namenode_id",
            "value" : "63"
          }, {
            "name" : "role_jceks_password",
            "value" : "7t8uwyatl47lvm6s5zl96ctml"
          } ]
        }
      } ],
      "displayName" : "HDFS"
    }, {
      "name" : "sentry",
      "type" : "SENTRY",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "SENTRY_SERVER",
          "items" : [ {
            "name" : "sentry_server_java_heapsize",
            "value" : "268435456"
          } ]
        } ],
        "items" : [ {
          "name" : "hdfs_service",
          "value" : "hdfs"
        }, {
          "name" : "sentry_server_database_host",
          "value" : "ip-172-32-1-224"
        }, {
          "name" : "sentry_server_database_password",
          "value" : "peperonata"
        }, {
          "name" : "sentry_service_admin_group",
          "value" : "hive,impala,hue,solr,kafka,hbase,diegomarcheselli"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "sentry-GATEWAY-99d29bc2fc4fa02e8e4b3f221bc9a101",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "a31c80ba-69df-49a3-abbf-707c10480e12"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "sentry-SENTRY_SERVER-7f375ac390d81812fd5fbd4b0a4c5bbd",
        "type" : "SENTRY_SERVER",
        "hostRef" : {
          "hostId" : "d52e9214-b778-4f8e-85fd-f4139b7b15ed"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "6fstqavk6smeiock0nbsdmyh"
          } ]
        }
      } ],
      "displayName" : "Sentry"
    } ]
  } ],
  "hosts" : [ {
    "hostId" : "6afe0ad9-1a08-4457-bb9e-b5a39852e858",
    "ipAddress" : "172.32.1.137",
    "hostname" : "ip-172-32-1-137",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "5ad6242b-46df-4569-87a1-13f589e0ac39",
    "ipAddress" : "172.32.1.206",
    "hostname" : "ip-172-32-1-206",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "70f9859e-3adf-44a0-983f-5c683318ac36",
    "ipAddress" : "172.32.1.224",
    "hostname" : "ip-172-32-1-224",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "a31c80ba-69df-49a3-abbf-707c10480e12",
    "ipAddress" : "172.32.1.38",
    "hostname" : "ip-172-32-1-38",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "d52e9214-b778-4f8e-85fd-f4139b7b15ed",
    "ipAddress" : "172.32.1.56",
    "hostname" : "ip-172-32-1-56",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  } ],
  "users" : [ {
    "name" : "__cloudera_internal_user__hue-HUE_SERVER-3ee73173aa3523d37af280d911049cbb",
    "roles" : [ "ROLE_NAVIGATOR_ADMIN" ],
    "pwHash" : "9d48bbf37b3d940435ffa4b68057837c1a775613b53e9b4d54f19036381f5516",
    "pwSalt" : -479634338895430424,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-EVENTSERVER-3ee73173aa3523d37af280d911049cbb",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "1554e6dbc9a2401f753df82429147dc97892b72451c7276ee1756d99b6041219",
    "pwSalt" : -6466430185000564493,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-HOSTMONITOR-3ee73173aa3523d37af280d911049cbb",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "0bd8fa319fa7dd97f1b4233e7318f164c564a3717b0028439ff2aca792c94b95",
    "pwSalt" : -1531440993484671499,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-REPORTSMANAGER-3ee73173aa3523d37af280d911049cbb",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "579cdc68b3282a5b192eb476eb8f756ca1824fcdc5700c089e1daf9a5b6006dd",
    "pwSalt" : -4120789775080362609,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-SERVICEMONITOR-3ee73173aa3523d37af280d911049cbb",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "f7946eb3cf594f2ef5731c4d3a87104e684f0be99cb8979a4f04301d3e1b6ddf",
    "pwSalt" : -7004581711546983407,
    "pwLogin" : true
  }, {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ],
    "pwHash" : "7a2b7380ef0a01e23f52ff7785db195d58efd563a9b57cdb4c254211e53c4402",
    "pwSalt" : -2457111370927917633,
    "pwLogin" : true
  }, {
    "name" : "diegomarcheselli",
    "roles" : [ "ROLE_ADMIN" ],
    "pwHash" : "50f9b6eb16ee94b5dd4a96487dc5bdeffbab4ab9eaac44604f916c26bca0ea21",
    "pwSalt" : 8626912364789623461,
    "pwLogin" : true
  }, {
    "name" : "hdfs",
    "roles" : [ "ROLE_ADMIN" ],
    "pwHash" : "7b221edb0cd30bfc799e229dea7b916d0b3fa1e254642677573667a414e418fa",
    "pwSalt" : -3684938788170345552,
    "pwLogin" : true
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ],
    "pwHash" : "4aaaec501dfda98f0276077ac66f32ed92b035d6fca6ca9bcf1728b7a6ee319d",
    "pwSalt" : 726985320995324347,
    "pwLogin" : true
  } ],
  "versionInfo" : {
    "version" : "5.15.2",
    "buildUser" : "jenkins",
    "buildTimestamp" : "20181111-0722",
    "gitHash" : "bb8bf45c81fd454610b53e4945ceb482361f7568",
    "snapshot" : false
  },
  "managementService" : {
    "name" : "mgmt",
    "type" : "MGMT",
    "config" : {
      "roleTypeConfigs" : [ {
        "roleType" : "EVENTSERVER",
        "items" : [ {
          "name" : "event_server_heapsize",
          "value" : "617611264"
        } ]
      }, {
        "roleType" : "REPORTSMANAGER",
        "items" : [ {
          "name" : "headlamp_database_host",
          "value" : "172.32.1.224"
        }, {
          "name" : "headlamp_database_name",
          "value" : "rman"
        }, {
          "name" : "headlamp_database_password",
          "value" : "peperonata"
        }, {
          "name" : "headlamp_database_user",
          "value" : "rman"
        }, {
          "name" : "headlamp_heapsize",
          "value" : "617611264"
        } ]
      }, {
        "roleType" : "SERVICEMONITOR",
        "items" : [ {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "6442450944"
        } ]
      } ],
      "items" : [ ]
    },
    "roles" : [ {
      "name" : "mgmt-ALERTPUBLISHER-3ee73173aa3523d37af280d911049cbb",
      "type" : "ALERTPUBLISHER",
      "hostRef" : {
        "hostId" : "6afe0ad9-1a08-4457-bb9e-b5a39852e858"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "9z5qbfrecsokkccxluznicuru"
        } ]
      }
    }, {
      "name" : "mgmt-EVENTSERVER-3ee73173aa3523d37af280d911049cbb",
      "type" : "EVENTSERVER",
      "hostRef" : {
        "hostId" : "6afe0ad9-1a08-4457-bb9e-b5a39852e858"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "3g86uzig3qjvai9do9pbd0dk5"
        } ]
      }
    }, {
      "name" : "mgmt-HOSTMONITOR-3ee73173aa3523d37af280d911049cbb",
      "type" : "HOSTMONITOR",
      "hostRef" : {
        "hostId" : "6afe0ad9-1a08-4457-bb9e-b5a39852e858"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "ydarohtkeco9jy0rv90qodc1"
        } ]
      }
    }, {
      "name" : "mgmt-REPORTSMANAGER-3ee73173aa3523d37af280d911049cbb",
      "type" : "REPORTSMANAGER",
      "hostRef" : {
        "hostId" : "6afe0ad9-1a08-4457-bb9e-b5a39852e858"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "6kxazpxl663smdb7o5oipmxh8"
        } ]
      }
    }, {
      "name" : "mgmt-SERVICEMONITOR-3ee73173aa3523d37af280d911049cbb",
      "type" : "SERVICEMONITOR",
      "hostRef" : {
        "hostId" : "6afe0ad9-1a08-4457-bb9e-b5a39852e858"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "6w8c372ezh8ntf48v5zzcm9o5"
        } ]
      }
    } ],
    "displayName" : "Cloudera Management Service"
  },
  "managerSettings" : {
    "items" : [ {
      "name" : "AD_USE_SIMPLE_AUTH",
      "value" : "false"
    }, {
      "name" : "CLUSTER_STATS_START",
      "value" : "10/23/2012 0:30"
    }, {
      "name" : "KDC_ADMIN_HOST",
      "value" : "ip-172-32-1-224"
    }, {
      "name" : "KDC_ADMIN_PASSWORD",
      "value" : "BQIAAABLAAEACEFSREEuQ09NAAxjbG91ZGVyYS1zY20AAAABXGUv/wEAEgAg41R0fmhXc77ifpXScTHiCLmiEh9mGHGWlaq9y7d4v/MAAAAB"
    }, {
      "name" : "KDC_ADMIN_USER",
      "value" : "cloudera-scm@ARDA.COM"
    }, {
      "name" : "KDC_HOST",
      "value" : "ip-172-32-1-224"
    }, {
      "name" : "KRB_ENC_TYPES",
      "value" : "aes256-cts"
    }, {
      "name" : "PUBLIC_CLOUD_STATUS",
      "value" : "ON_PUBLIC_CLOUD"
    }, {
      "name" : "REMOTE_PARCEL_REPO_URLS",
      "value" : "https://archive.cloudera.com/cdh5/parcels/{latest_supported}/,https://archive.cloudera.com/cdh4/parcels/latest/,https://archive.cloudera.com/impala/parcels/latest/,https://archive.cloudera.com/search/parcels/latest/,https://archive.cloudera.com/accumulo/parcels/1.4/,https://archive.cloudera.com/accumulo-c5/parcels/latest/,https://archive.cloudera.com/kafka/parcels/latest/,http://archive.cloudera.com/kudu/parcels/latest/,https://archive.cloudera.com/spark/parcels/latest/,https://archive.cloudera.com/sqoop-connectors/parcels/latest/"
    }, {
      "name" : "SECURITY_REALM",
      "value" : "ARDA.COM"
    } ]
  }
}

```
