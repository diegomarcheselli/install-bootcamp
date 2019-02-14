## Best Terasort

```
apreduce.map.java.opts.max.heap =  819
mapreduce.reduce.java.opts.max.heap =  819
mapreduce.map.memory.mb =  1024
mapreduce.job.maps =  2
mapreduce.job.reduces =  8


TERASORT

real    1m18.871s
user    0m6.030s
sys     0m0.299s
```

## WORST Terasort

```
apreduce.map.java.opts.max.heap =  819
mapreduce.reduce.java.opts.max.heap =  819
mapreduce.map.memory.mb =  1024
mapreduce.job.maps =  4
mapreduce.job.reduces =  2


TERASORT

real    1m49.940s
user    0m6.232s
sys     0m0.264s
Deleted /user/diegomarcheselli/lab/tg-10GB-4-2-1024
Deleted /user/diegomarcheselli/lab/ts-10GB-4-2-1024
```

## Best Terage


```
apreduce.map.java.opts.max.heap =  819
mapreduce.reduce.java.opts.max.heap =  819
mapreduce.map.memory.mb =  1024
mapreduce.job.maps =  8
mapreduce.job.reduces =  2

TERAGEN

real    0m35.797s
user    0m4.748s
sys     0m0.225s
```


## Worst Terage


```
apreduce.map.java.opts.max.heap =  819
mapreduce.reduce.java.opts.max.heap =  819
mapreduce.map.memory.mb =  1024
mapreduce.job.maps =  8
mapreduce.job.reduces =  2

TERAGEN

real    0m35.797s
user    0m4.748s
sys     0m0.225s
```
