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



[ec2-user@ip-172-32-1-28 ~]$ sudo cat /etc/passwd | grep denali
denali:x:3900:1001::/home/denali:/bin/bash

[ec2-user@ip-172-32-1-249 ~]$ sudo cat /etc/passwd | grep denali
denali:x:3900:1001::/home/denali:/bin/bash

[ec2-user@ip-172-32-1-214 ~]$ sudo cat /etc/passwd | grep denali
denali:x:3900:1001::/home/denali:/bin/bash

[ec2-user@ip-172-32-1-203 ~]$ sudo cat /etc/passw
d | grep denali
denali:x:3900:1001::/home/denali:/bin/bash
[ec2-user@ip-172-32-1-236 ~]$ sudo cat /etc/passwd | grep denali
denali:x:3900:1001::/home/denali:/bin/bash




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
---

## Linux version


```
ansible all -a 'cat /etc/redhat-release'
172.32.1.203 | CHANGED | rc=0 >>
Red Hat Enterprise Linux Server release 7.6 (Maipo)

172.32.1.28 | CHANGED | rc=0 >>
Red Hat Enterprise Linux Server release 7.6 (Maipo)

172.32.1.214 | CHANGED | rc=0 >>
Red Hat Enterprise Linux Server release 7.6 (Maipo)

172.32.1.236 | CHANGED | rc=0 >>
Red Hat Enterprise Linux Server release 7.6 (Maipo)

172.32.1.249 | CHANGED | rc=0 >>
Red Hat Enterprise Linux Server release 7.6 (Maipo)



[ec2-user@ip-172-32-1-28 ~]$ sudo cat /etc/passwd | grep rocky
rocky:x:3800:1002::/home/rocky:/bin/bash

[ec2-user@ip-172-32-1-249 ~]$ sudo cat /etc/passwd | grep rocky
rocky:x:3800:1002::/home/rocky:/bin/bash

[ec2-user@ip-172-32-1-214 ~]$ sudo cat /etc/passwd | grep rocky
rocky:x:3800:1002::/home/rocky:/bin/bash

[ec2-user@ip-172-32-1-203 ~]$ sudo cat /etc/passwd | grep rocky
rocky:x:3800:1002::/home/rocky:/bin/bash

[ec2-user@ip-172-32-1-236 ~]$ sudo cat /etc/passwd | grep rocky
rocky:x:3800:1002::/home/rocky:/bin/bash

```

## Alaska group

```
[ec2-user@ip-172-32-1-28 ~]$ sudo cat /etc/group | grep alaska
alaska:x:1001:

[ec2-user@ip-172-32-1-249 ~]$  sudo cat /etc/group | grep alaska
alaska:x:1001:

[ec2-user@ip-172-32-1-214 ~]$  sudo cat /etc/group | grep alaska
alaska:x:1001:

[ec2-user@ip-172-32-1-203 ~]$  sudo cat /etc/group | grep alaska
alaska:x:1001:

[ec2-user@ip-172-32-1-236 ~]$  sudo cat /etc/group | grep alaska
alaska:x:1001:




```

## Colorado  group

```
[ec2-user@ip-172-32-1-28 ~]$ sudo cat /etc/group | grep colorado
colorado:x:1002:

[ec2-user@ip-172-32-1-249 ~]$  sudo cat /etc/group | grep colorado
colorado:x:1002:


[ec2-user@ip-172-32-1-214 ~]$  sudo cat /etc/group | grep colorado
colorado:x:1002:

[ec2-user@ip-172-32-1-203 ~]$  sudo cat /etc/group | grep colorado
colorado:x:1002:

[ec2-user@ip-172-32-1-236 ~]$  sudo cat /etc/group | grep colorado
colorado:x:1002:

```


## Instances

### IP

```
### INTERNAL

 172.32.1.28
 172.32.1.249
 172.32.1.214
 172.32.1.203
 172.32.1.236
 
 
 
 ### EXTERNAL
 
 52.17.175.96
34.247.84.230
18.203.100.207
34.241.53.115
34.249.104.53


```

### DNS


```
### INTERNAL

ip-172-32-1-28.eu-west-1.compute.internal
ip-172-32-1-249.eu-west-1.compute.internal
ip-172-32-1-214.eu-west-1.compute.internal
ip-172-32-1-203.eu-west-1.compute.internal
ip-172-32-1-236.eu-west-1.compute.internal
 
 
 
 ### EXTERNAL
 
ec2-52-17-175-96.eu-west-1.compute.amazonaws.com
ec2-34-247-84-230.eu-west-1.compute.amazonaws.com
ec2-18-203-100-207.eu-west-1.compute.amazonaws.com
ec2-34-241-53-115.eu-west-1.compute.amazonaws.com
ec2-34-249-104-53.eu-west-1.compute.amazonaws.com


```

### Volume capacity

```

[ec2-user@ip-172-32-1-28 ~]$ ansible all -a 'df -h'
172.32.1.236 | CHANGED | rc=0 >>
Filesystem      Size  Used Avail Use% Mounted on
/dev/nvme0n1p2   60G  1.8G   59G   3% /
devtmpfs        7.6G     0  7.6G   0% /dev
tmpfs           7.6G     0  7.6G   0% /dev/shm
tmpfs           7.6G   17M  7.6G   1% /run
tmpfs           7.6G     0  7.6G   0% /sys/fs/cgroup
tmpfs           1.6G     0  1.6G   0% /run/user/1000

172.32.1.249 | CHANGED | rc=0 >>
Filesystem      Size  Used Avail Use% Mounted on
/dev/nvme0n1p2   60G  1.8G   59G   3% /
devtmpfs        7.6G     0  7.6G   0% /dev
tmpfs           7.6G     0  7.6G   0% /dev/shm
tmpfs           7.6G   17M  7.6G   1% /run
tmpfs           7.6G     0  7.6G   0% /sys/fs/cgroup
tmpfs           1.6G     0  1.6G   0% /run/user/1000

172.32.1.28 | CHANGED | rc=0 >>
Filesystem      Size  Used Avail Use% Mounted on
/dev/nvme0n1p2   60G  1.9G   59G   4% /
devtmpfs        7.6G     0  7.6G   0% /dev
tmpfs           7.6G  124K  7.6G   1% /dev/shm
tmpfs           7.6G   17M  7.6G   1% /run
tmpfs           7.6G     0  7.6G   0% /sys/fs/cgroup
tmpfs           1.6G     0  1.6G   0% /run/user/1000

172.32.1.214 | CHANGED | rc=0 >>
Filesystem      Size  Used Avail Use% Mounted on
/dev/nvme0n1p2   60G  1.8G   59G   3% /
devtmpfs        7.6G     0  7.6G   0% /dev
tmpfs           7.6G     0  7.6G   0% /dev/shm
tmpfs           7.6G   17M  7.6G   1% /run
tmpfs           7.6G     0  7.6G   0% /sys/fs/cgroup
tmpfs           1.6G     0  1.6G   0% /run/user/1000

172.32.1.203 | CHANGED | rc=0 >>
Filesystem      Size  Used Avail Use% Mounted on
/dev/nvme0n1p2   60G  1.8G   59G   3% /
devtmpfs        7.6G     0  7.6G   0% /dev
tmpfs           7.6G     0  7.6G   0% /dev/shm
tmpfs           7.6G   17M  7.6G   1% /run
tmpfs           7.6G     0  7.6G   0% /sys/fs/cgroup
tmpfs           1.6G     0  1.6G   0% /run/user/1000

```


### Repolist


```

[ec2-user@ip-172-32-1-28 ~]$ ansible all -a 'yum repolist enabled'
 [WARNING]: Consider using the yum module rather than running yum.  If you need to use command because yum is insufficient you can add warn=False to
this command task or set command_warnings=False in ansible.cfg to get rid of this message.

172.32.1.28 | FAILED | rc=1 >>
Loaded plugins: amazon-id, rhui-lb, search-disabled-repos
Could not contact CDS load balancer rhui2-cds01.eu-west-1.aws.ce.redhat.com, trying others.Repo rhui-REGION-client-config-server-7 forced skip_if_unavailable=True due to: /etc/pki/rhui/cdn.redhat.com-chain.crt
Repo rhui-REGION-client-config-server-7 forced skip_if_unavailable=True due to: /etc/pki/rhui/product/rhui-client-config-server-7.crt
Repo rhui-REGION-client-config-server-7 forced skip_if_unavailable=True due to: /etc/pki/rhui/rhui-client-config-server-7.key
Repo rhui-REGION-rhel-server-releases forced skip_if_unavailable=True due to: /etc/pki/rhui/cdn.redhat.com-chain.crt
Repo rhui-REGION-rhel-server-releases forced skip_if_unavailable=True due to: /etc/pki/rhui/product/content-rhel7.crt
Repo rhui-REGION-rhel-server-releases forced skip_if_unavailable=True due to: /etc/pki/rhui/content-rhel7.key
Repo rhui-REGION-rhel-server-rh-common forced skip_if_unavailable=True due to: /etc/pki/rhui/cdn.redhat.com-chain.crt
Repo rhui-REGION-rhel-server-rh-common forced skip_if_unavailable=True due to: /etc/pki/rhui/product/content-rhel7.crt
Repo rhui-REGION-rhel-server-rh-common forced skip_if_unavailable=True due to: /etc/pki/rhui/content-rhel7.key


Could not contact any CDS load balancers: rhui2-cds01.eu-west-1.aws.ce.redhat.com, rhui2-cds02.eu-west-1.aws.ce.redhat.com.non-zero return code

172.32.1.203 | FAILED | rc=1 >>
Loaded plugins: amazon-id, rhui-lb, search-disabled-repos
Could not contact CDS load balancer rhui2-cds01.eu-west-1.aws.ce.redhat.com, trying others.Repo rhui-REGION-client-config-server-7 forced skip_if_unavailable=True due to: /etc/pki/rhui/cdn.redhat.com-chain.crt
Repo rhui-REGION-client-config-server-7 forced skip_if_unavailable=True due to: /etc/pki/rhui/product/rhui-client-config-server-7.crt
Repo rhui-REGION-client-config-server-7 forced skip_if_unavailable=True due to: /etc/pki/rhui/rhui-client-config-server-7.key
Repo rhui-REGION-rhel-server-releases forced skip_if_unavailable=True due to: /etc/pki/rhui/cdn.redhat.com-chain.crt
Repo rhui-REGION-rhel-server-releases forced skip_if_unavailable=True due to: /etc/pki/rhui/product/content-rhel7.crt
Repo rhui-REGION-rhel-server-releases forced skip_if_unavailable=True due to: /etc/pki/rhui/content-rhel7.key
Repo rhui-REGION-rhel-server-rh-common forced skip_if_unavailable=True due to: /etc/pki/rhui/cdn.redhat.com-chain.crt
Repo rhui-REGION-rhel-server-rh-common forced skip_if_unavailable=True due to: /etc/pki/rhui/product/content-rhel7.crt
Repo rhui-REGION-rhel-server-rh-common forced skip_if_unavailable=True due to: /etc/pki/rhui/content-rhel7.key


Could not contact any CDS load balancers: rhui2-cds01.eu-west-1.aws.ce.redhat.com, rhui2-cds02.eu-west-1.aws.ce.redhat.com.non-zero return code

172.32.1.214 | FAILED | rc=1 >>
Loaded plugins: amazon-id, rhui-lb, search-disabled-repos
Could not contact CDS load balancer rhui2-cds01.eu-west-1.aws.ce.redhat.com, trying others.Repo rhui-REGION-client-config-server-7 forced skip_if_unavailable=True due to: /etc/pki/rhui/cdn.redhat.com-chain.crt
Repo rhui-REGION-client-config-server-7 forced skip_if_unavailable=True due to: /etc/pki/rhui/product/rhui-client-config-server-7.crt
Repo rhui-REGION-client-config-server-7 forced skip_if_unavailable=True due to: /etc/pki/rhui/rhui-client-config-server-7.key
Repo rhui-REGION-rhel-server-releases forced skip_if_unavailable=True due to: /etc/pki/rhui/cdn.redhat.com-chain.crt
Repo rhui-REGION-rhel-server-releases forced skip_if_unavailable=True due to: /etc/pki/rhui/product/content-rhel7.crt
Repo rhui-REGION-rhel-server-releases forced skip_if_unavailable=True due to: /etc/pki/rhui/content-rhel7.key
Repo rhui-REGION-rhel-server-rh-common forced skip_if_unavailable=True due to: /etc/pki/rhui/cdn.redhat.com-chain.crt
Repo rhui-REGION-rhel-server-rh-common forced skip_if_unavailable=True due to: /etc/pki/rhui/product/content-rhel7.crt
Repo rhui-REGION-rhel-server-rh-common forced skip_if_unavailable=True due to: /etc/pki/rhui/content-rhel7.key


Could not contact any CDS load balancers: rhui2-cds01.eu-west-1.aws.ce.redhat.com, rhui2-cds02.eu-west-1.aws.ce.redhat.com.non-zero return code

172.32.1.249 | FAILED | rc=1 >>
Loaded plugins: amazon-id, rhui-lb, search-disabled-repos
Could not contact CDS load balancer rhui2-cds01.eu-west-1.aws.ce.redhat.com, trying others.Repo rhui-REGION-client-config-server-7 forced skip_if_unavailable=True due to: /etc/pki/rhui/cdn.redhat.com-chain.crt
Repo rhui-REGION-client-config-server-7 forced skip_if_unavailable=True due to: /etc/pki/rhui/product/rhui-client-config-server-7.crt
Repo rhui-REGION-client-config-server-7 forced skip_if_unavailable=True due to: /etc/pki/rhui/rhui-client-config-server-7.key
Repo rhui-REGION-rhel-server-releases forced skip_if_unavailable=True due to: /etc/pki/rhui/cdn.redhat.com-chain.crt
Repo rhui-REGION-rhel-server-releases forced skip_if_unavailable=True due to: /etc/pki/rhui/product/content-rhel7.crt
Repo rhui-REGION-rhel-server-releases forced skip_if_unavailable=True due to: /etc/pki/rhui/content-rhel7.key
Repo rhui-REGION-rhel-server-rh-common forced skip_if_unavailable=True due to: /etc/pki/rhui/cdn.redhat.com-chain.crt
Repo rhui-REGION-rhel-server-rh-common forced skip_if_unavailable=True due to: /etc/pki/rhui/product/content-rhel7.crt
Repo rhui-REGION-rhel-server-rh-common forced skip_if_unavailable=True due to: /etc/pki/rhui/content-rhel7.key


Could not contact any CDS load balancers: rhui2-cds01.eu-west-1.aws.ce.redhat.com, rhui2-cds02.eu-west-1.aws.ce.redhat.com.non-zero return code

172.32.1.236 | FAILED | rc=1 >>
Loaded plugins: amazon-id, rhui-lb, search-disabled-repos
Could not contact CDS load balancer rhui2-cds01.eu-west-1.aws.ce.redhat.com, trying others.Repo rhui-REGION-client-config-server-7 forced skip_if_unavailable=True due to: /etc/pki/rhui/cdn.redhat.com-chain.crt
Repo rhui-REGION-client-config-server-7 forced skip_if_unavailable=True due to: /etc/pki/rhui/product/rhui-client-config-server-7.crt
Repo rhui-REGION-client-config-server-7 forced skip_if_unavailable=True due to: /etc/pki/rhui/rhui-client-config-server-7.key
Repo rhui-REGION-rhel-server-releases forced skip_if_unavailable=True due to: /etc/pki/rhui/cdn.redhat.com-chain.crt
Repo rhui-REGION-rhel-server-releases forced skip_if_unavailable=True due to: /etc/pki/rhui/product/content-rhel7.crt
Repo rhui-REGION-rhel-server-releases forced skip_if_unavailable=True due to: /etc/pki/rhui/content-rhel7.key
Repo rhui-REGION-rhel-server-rh-common forced skip_if_unavailable=True due to: /etc/pki/rhui/cdn.redhat.com-chain.crt
Repo rhui-REGION-rhel-server-rh-common forced skip_if_unavailable=True due to: /etc/pki/rhui/product/content-rhel7.crt
Repo rhui-REGION-rhel-server-rh-common forced skip_if_unavailable=True due to: /etc/pki/rhui/content-rhel7.key


Could not contact any CDS load balancers: rhui2-cds01.eu-west-1.aws.ce.redhat.com, rhui2-cds02.eu-west-1.aws.ce.redhat.com.non-zero return code


```




