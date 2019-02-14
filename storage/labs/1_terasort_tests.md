# Terrasort Test

## User

```
ansible all --become -m shell  -a ' cat /etc/passwd | grep diegomarcheselli'
```
```
172.32.1.38 | CHANGED | rc=0 >>
diegomarcheselli:x:1001:1001::/home/diegomarcheselli:/bin/bash

172.32.1.224 | CHANGED | rc=0 >>
diegomarcheselli:x:1001:1001::/home/diegomarcheselli:/bin/bash

172.32.1.137 | CHANGED | rc=0 >>
diegomarcheselli:x:1001:1001::/home/diegomarcheselli:/bin/bash

172.32.1.56 | CHANGED | rc=0 >>
diegomarcheselli:x:1001:1001::/home/diegomarcheselli:/bin/bash

172.32.1.206 | CHANGED | rc=0 >>
diegomarcheselli:x:1001:1001::/home/diegomarcheselli:/bin/bash
```





## Teragen

```
time hadoop jar  /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen \
>     -Ddfs.block.size=32000000 \
>     -Dmapred.map.tasks=4 \
>     100000000 \
>     /user/diegomarcheselli/teragen
```
```

19/02/12 18:13:18 INFO client.RMProxy: Connecting to ResourceManager at ip-172-32-1-137/172.32.1.137:8032
19/02/12 18:13:18 INFO terasort.TeraGen: Generating 100000000 using 4
19/02/12 18:13:18 INFO mapreduce.JobSubmitter: number of splits:4
19/02/12 18:13:18 INFO Configuration.deprecation: mapred.map.tasks is deprecated. Instead, use mapreduce.job.maps
19/02/12 18:13:18 INFO Configuration.deprecation: dfs.block.size is deprecated. Instead, use dfs.blocksize
19/02/12 18:13:18 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1549980239113_0007
19/02/12 18:13:18 INFO impl.YarnClientImpl: Submitted application application_1549980239113_0007
19/02/12 18:13:18 INFO mapreduce.Job: The url to track the job: http://ip-172-32-1-137:8088/proxy/application_1549980239113_0007/
19/02/12 18:13:18 INFO mapreduce.Job: Running job: job_1549980239113_0007
19/02/12 18:13:23 INFO mapreduce.Job: Job job_1549980239113_0007 running in uber mode : false
19/02/12 18:13:23 INFO mapreduce.Job:  map 0% reduce 0%
19/02/12 18:13:40 INFO mapreduce.Job:  map 12% reduce 0%
19/02/12 18:13:42 INFO mapreduce.Job:  map 35% reduce 0%
19/02/12 18:13:46 INFO mapreduce.Job:  map 41% reduce 0%
19/02/12 18:13:48 INFO mapreduce.Job:  map 54% reduce 0%
19/02/12 18:13:52 INFO mapreduce.Job:  map 59% reduce 0%
19/02/12 18:13:54 INFO mapreduce.Job:  map 70% reduce 0%
19/02/12 18:13:57 INFO mapreduce.Job:  map 72% reduce 0%
19/02/12 18:14:00 INFO mapreduce.Job:  map 78% reduce 0%
19/02/12 18:14:06 INFO mapreduce.Job:  map 85% reduce 0%
19/02/12 18:14:12 INFO mapreduce.Job:  map 92% reduce 0%
19/02/12 18:14:17 INFO mapreduce.Job:  map 95% reduce 0%
19/02/12 18:14:18 INFO mapreduce.Job:  map 100% reduce 0%
19/02/12 18:14:19 INFO mapreduce.Job: Job job_1549980239113_0007 completed successfully
19/02/12 18:14:19 INFO mapreduce.Job: Counters: 31
        File System Counters
                FILE: Number of bytes read=0
                FILE: Number of bytes written=596360
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=344
                HDFS: Number of bytes written=10000000000
                HDFS: Number of read operations=16
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=8
        Job Counters
                Launched map tasks=4
                Other local map tasks=4
                Total time spent by all maps in occupied slots (ms)=188368
                Total time spent by all reduces in occupied slots (ms)=0
                Total time spent by all map tasks (ms)=188368
                Total vcore-milliseconds taken by all map tasks=188368
                Total megabyte-milliseconds taken by all map tasks=192888832
        Map-Reduce Framework
                Map input records=100000000
                Map output records=100000000
                Input split bytes=344
                Spilled Records=0
                Failed Shuffles=0
                Merged Map outputs=0
                GC time elapsed (ms)=1610
                CPU time spent (ms)=124940
                Physical memory (bytes) snapshot=959614976
                Virtual memory (bytes) snapshot=6341783552
                Total committed heap usage (bytes)=973602816
        org.apache.hadoop.examples.terasort.TeraGen$Counters
                CHECKSUM=214760662691937609
        File Input Format Counters
                Bytes Read=0
        File Output Format Counters
                Bytes Written=10000000000

real    1m3.152s
user    0m4.163s
sys     0m0.225s
```





## Terasort

## 

```
time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar terasort /user/diegomarcheselli/teragen /user/diegomarcheselli/teragen-output
```

```
19/02/12 18:28:47 INFO terasort.TeraSort: starting
19/02/12 18:28:48 INFO input.FileInputFormat: Total input paths to process : 4
Spent 169ms computing base-splits.
Spent 5ms computing TeraScheduler splits.
Computing input splits took 175ms
Sampling 10 splits of 316
Making 8 from 100000 sampled records
Computing parititions took 552ms
Spent 729ms computing partitions.
19/02/12 18:28:49 INFO client.RMProxy: Connecting to ResourceManager at ip-172-32-1-137/172.32.1.137:8032
19/02/12 18:28:49 INFO mapreduce.JobSubmitter: number of splits:316
19/02/12 18:28:49 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1549980239113_0008
19/02/12 18:28:49 INFO impl.YarnClientImpl: Submitted application application_1549980239113_0008
19/02/12 18:28:49 INFO mapreduce.Job: The url to track the job: http://ip-172-32-1-137:8088/proxy/application_1549980239113_0008/
19/02/12 18:28:49 INFO mapreduce.Job: Running job: job_1549980239113_0008
19/02/12 18:28:55 INFO mapreduce.Job: Job job_1549980239113_0008 running in uber mode : false
19/02/12 18:28:55 INFO mapreduce.Job:  map 0% reduce 0%
19/02/12 18:29:04 INFO mapreduce.Job:  map 1% reduce 0%
19/02/12 18:29:05 INFO mapreduce.Job:  map 3% reduce 0%
19/02/12 18:29:06 INFO mapreduce.Job:  map 5% reduce 0%
19/02/12 18:29:12 INFO mapreduce.Job:  map 6% reduce 0%
19/02/12 18:29:13 INFO mapreduce.Job:  map 8% reduce 0%
19/02/12 18:29:14 INFO mapreduce.Job:  map 9% reduce 0%
19/02/12 18:29:20 INFO mapreduce.Job:  map 10% reduce 0%
19/02/12 18:29:23 INFO mapreduce.Job:  map 12% reduce 0%
19/02/12 18:29:24 INFO mapreduce.Job:  map 14% reduce 0%
19/02/12 18:29:27 INFO mapreduce.Job:  map 15% reduce 0%
19/02/12 18:29:32 INFO mapreduce.Job:  map 17% reduce 0%
19/02/12 18:29:33 INFO mapreduce.Job:  map 19% reduce 0%
19/02/12 18:29:34 INFO mapreduce.Job:  map 20% reduce 0%
19/02/12 18:29:40 INFO mapreduce.Job:  map 21% reduce 0%
19/02/12 18:29:41 INFO mapreduce.Job:  map 24% reduce 0%
19/02/12 18:29:42 INFO mapreduce.Job:  map 25% reduce 0%
19/02/12 18:29:49 INFO mapreduce.Job:  map 26% reduce 0%
19/02/12 18:29:50 INFO mapreduce.Job:  map 28% reduce 0%
19/02/12 18:29:51 INFO mapreduce.Job:  map 29% reduce 0%
19/02/12 18:29:55 INFO mapreduce.Job:  map 30% reduce 0%
19/02/12 18:29:56 INFO mapreduce.Job:  map 31% reduce 0%
19/02/12 18:29:59 INFO mapreduce.Job:  map 33% reduce 0%
19/02/12 18:30:00 INFO mapreduce.Job:  map 34% reduce 0%
19/02/12 18:30:02 INFO mapreduce.Job:  map 35% reduce 0%
19/02/12 18:30:06 INFO mapreduce.Job:  map 36% reduce 0%
19/02/12 18:30:09 INFO mapreduce.Job:  map 38% reduce 0%
19/02/12 18:30:10 INFO mapreduce.Job:  map 40% reduce 0%
19/02/12 18:30:15 INFO mapreduce.Job:  map 41% reduce 0%
19/02/12 18:30:17 INFO mapreduce.Job:  map 42% reduce 0%
19/02/12 18:30:18 INFO mapreduce.Job:  map 44% reduce 0%
19/02/12 18:30:19 INFO mapreduce.Job:  map 45% reduce 0%
19/02/12 18:30:24 INFO mapreduce.Job:  map 46% reduce 0%
19/02/12 18:30:25 INFO mapreduce.Job:  map 47% reduce 0%
19/02/12 18:30:26 INFO mapreduce.Job:  map 48% reduce 0%
19/02/12 18:30:27 INFO mapreduce.Job:  map 49% reduce 0%
19/02/12 18:30:28 INFO mapreduce.Job:  map 50% reduce 0%
19/02/12 18:30:31 INFO mapreduce.Job:  map 51% reduce 0%
19/02/12 18:30:32 INFO mapreduce.Job:  map 52% reduce 0%
19/02/12 18:30:36 INFO mapreduce.Job:  map 53% reduce 0%
19/02/12 18:30:37 INFO mapreduce.Job:  map 54% reduce 0%
19/02/12 18:30:38 INFO mapreduce.Job:  map 55% reduce 0%
19/02/12 18:30:39 INFO mapreduce.Job:  map 56% reduce 0%
19/02/12 18:30:42 INFO mapreduce.Job:  map 57% reduce 0%
19/02/12 18:30:45 INFO mapreduce.Job:  map 59% reduce 0%
19/02/12 18:30:46 INFO mapreduce.Job:  map 60% reduce 0%
19/02/12 18:30:48 INFO mapreduce.Job:  map 61% reduce 0%
19/02/12 18:30:51 INFO mapreduce.Job:  map 62% reduce 0%
19/02/12 18:30:53 INFO mapreduce.Job:  map 63% reduce 0%
19/02/12 18:30:54 INFO mapreduce.Job:  map 65% reduce 0%
19/02/12 18:30:56 INFO mapreduce.Job:  map 66% reduce 0%
19/02/12 18:31:00 INFO mapreduce.Job:  map 67% reduce 0%
19/02/12 18:31:02 INFO mapreduce.Job:  map 68% reduce 0%
19/02/12 18:31:03 INFO mapreduce.Job:  map 69% reduce 0%
19/02/12 18:31:04 INFO mapreduce.Job:  map 70% reduce 0%
19/02/12 18:31:06 INFO mapreduce.Job:  map 71% reduce 0%
19/02/12 18:31:07 INFO mapreduce.Job:  map 72% reduce 0%
19/02/12 18:31:10 INFO mapreduce.Job:  map 73% reduce 0%
19/02/12 18:31:12 INFO mapreduce.Job:  map 74% reduce 0%
19/02/12 18:31:13 INFO mapreduce.Job:  map 75% reduce 0%
19/02/12 18:31:14 INFO mapreduce.Job:  map 76% reduce 0%
19/02/12 18:31:15 INFO mapreduce.Job:  map 77% reduce 0%
19/02/12 18:31:19 INFO mapreduce.Job:  map 78% reduce 0%
19/02/12 18:31:20 INFO mapreduce.Job:  map 79% reduce 0%
19/02/12 18:31:21 INFO mapreduce.Job:  map 80% reduce 0%
19/02/12 18:31:23 INFO mapreduce.Job:  map 81% reduce 0%
19/02/12 18:31:24 INFO mapreduce.Job:  map 82% reduce 0%
19/02/12 18:31:28 INFO mapreduce.Job:  map 83% reduce 0%
19/02/12 18:31:29 INFO mapreduce.Job:  map 84% reduce 0%
19/02/12 18:31:31 INFO mapreduce.Job:  map 85% reduce 0%
19/02/12 18:31:33 INFO mapreduce.Job:  map 86% reduce 0%
19/02/12 18:31:40 INFO mapreduce.Job:  map 87% reduce 0%
19/02/12 18:31:41 INFO mapreduce.Job:  map 88% reduce 6%
19/02/12 18:31:42 INFO mapreduce.Job:  map 89% reduce 6%
19/02/12 18:31:43 INFO mapreduce.Job:  map 89% reduce 9%
19/02/12 18:31:44 INFO mapreduce.Job:  map 89% reduce 16%
19/02/12 18:31:46 INFO mapreduce.Job:  map 89% reduce 20%
19/02/12 18:31:47 INFO mapreduce.Job:  map 89% reduce 24%
19/02/12 18:31:48 INFO mapreduce.Job:  map 90% reduce 24%
19/02/12 18:31:49 INFO mapreduce.Job:  map 91% reduce 25%
19/02/12 18:31:50 INFO mapreduce.Job:  map 91% reduce 26%
19/02/12 18:31:53 INFO mapreduce.Job:  map 92% reduce 26%
19/02/12 18:31:56 INFO mapreduce.Job:  map 92% reduce 27%
19/02/12 18:31:58 INFO mapreduce.Job:  map 93% reduce 27%
19/02/12 18:31:59 INFO mapreduce.Job:  map 95% reduce 27%
19/02/12 18:32:03 INFO mapreduce.Job:  map 95% reduce 28%
19/02/12 18:32:05 INFO mapreduce.Job:  map 96% reduce 28%
19/02/12 18:32:07 INFO mapreduce.Job:  map 97% reduce 28%
19/02/12 18:32:09 INFO mapreduce.Job:  map 98% reduce 28%
19/02/12 18:32:11 INFO mapreduce.Job:  map 99% reduce 29%
19/02/12 18:32:15 INFO mapreduce.Job:  map 100% reduce 29%
19/02/12 18:32:17 INFO mapreduce.Job:  map 100% reduce 40%
19/02/12 18:32:19 INFO mapreduce.Job:  map 100% reduce 44%
19/02/12 18:32:20 INFO mapreduce.Job:  map 100% reduce 49%
19/02/12 18:32:21 INFO mapreduce.Job:  map 100% reduce 54%
19/02/12 18:32:22 INFO mapreduce.Job:  map 100% reduce 59%
19/02/12 18:32:23 INFO mapreduce.Job:  map 100% reduce 64%
19/02/12 18:32:25 INFO mapreduce.Job:  map 100% reduce 69%
19/02/12 18:32:26 INFO mapreduce.Job:  map 100% reduce 71%
19/02/12 18:32:27 INFO mapreduce.Job:  map 100% reduce 73%
19/02/12 18:32:28 INFO mapreduce.Job:  map 100% reduce 75%
19/02/12 18:32:29 INFO mapreduce.Job:  map 100% reduce 80%
19/02/12 18:32:30 INFO mapreduce.Job:  map 100% reduce 82%
19/02/12 18:32:31 INFO mapreduce.Job:  map 100% reduce 89%
19/02/12 18:32:35 INFO mapreduce.Job:  map 100% reduce 92%
19/02/12 18:32:37 INFO mapreduce.Job:  map 100% reduce 95%
19/02/12 18:32:38 INFO mapreduce.Job:  map 100% reduce 96%
19/02/12 18:32:40 INFO mapreduce.Job:  map 100% reduce 97%
19/02/12 18:32:43 INFO mapreduce.Job:  map 100% reduce 99%
19/02/12 18:32:46 INFO mapreduce.Job:  map 100% reduce 100%
19/02/12 18:32:46 INFO mapreduce.Job: Job job_1549980239113_0008 completed successfully
19/02/12 18:32:46 INFO mapreduce.Job: Counters: 50
        File System Counters
                FILE: Number of bytes read=4444290511
                FILE: Number of bytes written=8835770161
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=10000042660
                HDFS: Number of bytes written=10000000000
                HDFS: Number of read operations=972
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=16
        Job Counters
                Launched map tasks=316
                Launched reduce tasks=8
                Data-local map tasks=315
                Rack-local map tasks=1
                Total time spent by all maps in occupied slots (ms)=2252741
                Total time spent by all reduces in occupied slots (ms)=501491
                Total time spent by all map tasks (ms)=2252741
                Total time spent by all reduce tasks (ms)=501491
                Total vcore-milliseconds taken by all map tasks=2252741
                Total vcore-milliseconds taken by all reduce tasks=501491
                Total megabyte-milliseconds taken by all map tasks=2306806784
                Total megabyte-milliseconds taken by all reduce tasks=513526784
        Map-Reduce Framework
                Map input records=100000000
                Map output records=100000000
                Map output bytes=10200000000
                Map output materialized bytes=4342628872
                Input split bytes=42660
                Combine input records=0
                Combine output records=0
                Reduce input groups=100000000
                Reduce shuffle bytes=4342628872
                Reduce input records=100000000
                Reduce output records=100000000
                Spilled Records=200000000
                Shuffled Maps =2528
                Failed Shuffles=0
                Merged Map outputs=2528
                GC time elapsed (ms)=47716
                CPU time spent (ms)=1150860
                Physical memory (bytes) snapshot=167761850368
                Virtual memory (bytes) snapshot=511935246336
                Total committed heap usage (bytes)=187194933248
        Shuffle Errors
                BAD_ID=0
                CONNECTION=0
                IO_ERROR=0
                WRONG_LENGTH=0
                WRONG_MAP=0
                WRONG_REDUCE=0
        File Input Format Counters
                Bytes Read=10000000000
        File Output Format Counters
                Bytes Written=10000000000
19/02/12 18:32:46 INFO terasort.TeraSort: done

real    4m0.058s
user    0m6.525s
sys     0m0.241s

```



