## creating grups and users

sudo groupadd alaska
sudo groupadd colorado

sudo useradd -u 3900 -g alaska  denali
sudo useradd -u 3800 -g colorado  rocky

### denali

```
[ec2-user@ip-172-32-1-28 ~]$  ansible cluster -a  'id denali'
172.32.1.236 | CHANGED | rc=0 >>
uid=3900(denali) gid=1001(alaska) groups=1001(alaska)

172.32.1.214 | CHANGED | rc=0 >>
uid=3900(denali) gid=1001(alaska) groups=1001(alaska)

172.32.1.28 | CHANGED | rc=0 >>
uid=3900(denali) gid=1001(alaska) groups=1001(alaska)

172.32.1.249 | CHANGED | rc=0 >>
uid=3900(denali) gid=1001(alaska) groups=1001(alaska)

172.32.1.203 | CHANGED | rc=0 >>
uid=3900(denali) gid=1001(alaska) groups=1001(alaska)
```

### rocky


```
[ec2-user@ip-172-32-1-28 ~]$  ansible cluster -a  'id rocky'
172.32.1.249 | CHANGED | rc=0 >>
uid=3800(rocky) gid=1002(colorado) groups=1002(colorado)

172.32.1.236 | CHANGED | rc=0 >>
uid=3800(rocky) gid=1002(colorado) groups=1002(colorado)

172.32.1.28 | CHANGED | rc=0 >>
uid=3800(rocky) gid=1002(colorado) groups=1002(colorado)

172.32.1.214 | CHANGED | rc=0 >>
uid=3800(rocky) gid=1002(colorado) groups=1002(colorado)

172.32.1.203 | CHANGED | rc=0 >>
uid=3800(rocky) gid=1002(colorado) groups=1002(colorado)

```

