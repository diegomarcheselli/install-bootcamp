# Cloud provider

AWS

Hosts:
```
ansible all -a 'hostname -f'
```


```
172.32.1.178 | CHANGED | rc=0 >>
ip-172-32-1-178

172.32.1.158 | CHANGED | rc=0 >>
ip-172-32-1-158

172.32.1.171 | CHANGED | rc=0 >>
ip-172-32-1-171

172.32.1.87 | CHANGED | rc=0 >>
ip-172-32-1-87

172.32.1.128 | CHANGED | rc=0 >>
ip-172-32-1-128

```

# Linux release

```
ansible all -a 'cat /etc/redhat-release'
```


```
172.32.1.158 | CHANGED | rc=0 >>
Red Hat Enterprise Linux Server release 7.6 (Maipo)

172.32.1.178 | CHANGED | rc=0 >>
Red Hat Enterprise Linux Server release 7.6 (Maipo)

172.32.1.87 | CHANGED | rc=0 >>
Red Hat Enterprise Linux Server release 7.6 (Maipo)

172.32.1.171 | CHANGED | rc=0 >>
Red Hat Enterprise Linux Server release 7.6 (Maipo)

172.32.1.128 | CHANGED | rc=0 >>
Red Hat Enterprise Linux Server release 7.6 (Maipo)
```
---

# 1 Swappines
Original Value
```
ansible all -a 'cat /proc/sys/vm/swappiness'
```


```
172.32.1.158 | CHANGED | rc=0 >>
30

172.32.1.178 | CHANGED | rc=0 >>
30

172.32.1.128 | CHANGED | rc=0 >>
30

172.32.1.87 | CHANGED | rc=0 >>
30

172.32.1.171 | CHANGED | rc=0 >>
30
```
run on every node
```
sudo bash -c "echo 'vm.swappiness = 1' >> /etc/sysctl.conf"
```
restart  nodes
```
ansible all -a 'cat /proc/sys/vm/swappiness'
```


```
172.32.1.158 | CHANGED | rc=0 >>
1

172.32.1.171 | CHANGED | rc=0 >>
1

172.32.1.128 | CHANGED | rc=0 >>
1

172.32.1.87 | CHANGED | rc=0 >>
1

172.32.1.178 | CHANGED | rc=0 >>
1
```
---

# 2 Volume Attributes

```
ansible all -a 'df -h'
```

```
172.32.1.178 | CHANGED | rc=0 >>
Filesystem      Size  Used Avail Use% Mounted on
/dev/nvme0n1p2   50G  5.0G   46G  10% /
devtmpfs        7.6G     0  7.6G   0% /dev
tmpfs           7.6G  124K  7.6G   1% /dev/shm
tmpfs           7.6G  8.5M  7.6G   1% /run
tmpfs           7.6G     0  7.6G   0% /sys/fs/cgroup
tmpfs           1.6G     0  1.6G   0% /run/user/997
tmpfs           1.6G     0  1.6G   0% /run/user/1000

172.32.1.171 | CHANGED | rc=0 >>
Filesystem      Size  Used Avail Use% Mounted on
/dev/nvme0n1p2   50G  3.0G   48G   6% /
devtmpfs        7.6G     0  7.6G   0% /dev
tmpfs           7.6G     0  7.6G   0% /dev/shm
tmpfs           7.6G  8.5M  7.6G   1% /run
tmpfs           7.6G     0  7.6G   0% /sys/fs/cgroup
tmpfs           1.6G     0  1.6G   0% /run/user/0
cm_processes    7.6G     0  7.6G   0% /run/cloudera-scm-agent/process
tmpfs           1.6G     0  1.6G   0% /run/user/1000

172.32.1.87 | CHANGED | rc=0 >>
Filesystem      Size  Used Avail Use% Mounted on
/dev/nvme0n1p2   50G  3.0G   48G   6% /
devtmpfs        7.6G     0  7.6G   0% /dev
tmpfs           7.6G     0  7.6G   0% /dev/shm
tmpfs           7.6G  8.5M  7.6G   1% /run
tmpfs           7.6G     0  7.6G   0% /sys/fs/cgroup
tmpfs           1.6G     0  1.6G   0% /run/user/0
cm_processes    7.6G     0  7.6G   0% /run/cloudera-scm-agent/process
tmpfs           1.6G     0  1.6G   0% /run/user/1000

172.32.1.128 | CHANGED | rc=0 >>
Filesystem      Size  Used Avail Use% Mounted on
/dev/nvme0n1p2   50G  3.0G   48G   6% /
devtmpfs        7.6G     0  7.6G   0% /dev
tmpfs           7.6G     0  7.6G   0% /dev/shm
tmpfs           7.6G  8.5M  7.6G   1% /run
tmpfs           7.6G     0  7.6G   0% /sys/fs/cgroup
tmpfs           1.6G     0  1.6G   0% /run/user/0
cm_processes    7.6G     0  7.6G   0% /run/cloudera-scm-agent/process
tmpfs           1.6G     0  1.6G   0% /run/user/1000

172.32.1.158 | CHANGED | rc=0 >>
Filesystem      Size  Used Avail Use% Mounted on
/dev/nvme0n1p2   50G  3.0G   48G   6% /
devtmpfs        7.6G     0  7.6G   0% /dev
tmpfs           7.6G     0  7.6G   0% /dev/shm
tmpfs           7.6G  8.5M  7.6G   1% /run
tmpfs           7.6G     0  7.6G   0% /sys/fs/cgroup
tmpfs           1.6G     0  1.6G   0% /run/user/0
cm_processes    7.6G     0  7.6G   0% /run/cloudera-scm-agent/process
tmpfs           1.6G     0  1.6G   0% /run/user/1000
```

```
ansible all -a 'lsblk'
```

```
172.32.1.171 | CHANGED | rc=0 >>
NAME        MAJ:MIN RM SIZE RO TYPE MOUNTPOINT
nvme0n1     259:0    0  50G  0 disk
├─nvme0n1p1 259:1    0   1M  0 part
└─nvme0n1p2 259:2    0  50G  0 part /

172.32.1.178 | CHANGED | rc=0 >>
NAME        MAJ:MIN RM SIZE RO TYPE MOUNTPOINT
nvme0n1     259:0    0  50G  0 disk
├─nvme0n1p1 259:1    0   1M  0 part
└─nvme0n1p2 259:2    0  50G  0 part /

172.32.1.87 | CHANGED | rc=0 >>
NAME        MAJ:MIN RM SIZE RO TYPE MOUNTPOINT
nvme0n1     259:0    0  50G  0 disk
├─nvme0n1p1 259:1    0   1M  0 part
└─nvme0n1p2 259:2    0  50G  0 part /

172.32.1.158 | CHANGED | rc=0 >>
NAME        MAJ:MIN RM SIZE RO TYPE MOUNTPOINT
nvme0n1     259:0    0  50G  0 disk
├─nvme0n1p1 259:1    0   1M  0 part
└─nvme0n1p2 259:2    0  50G  0 part /

172.32.1.128 | CHANGED | rc=0 >>
NAME        MAJ:MIN RM SIZE RO TYPE MOUNTPOINT
nvme0n1     259:0    0  50G  0 disk
├─nvme0n1p1 259:1    0   1M  0 part
└─nvme0n1p2 259:2    0  50G  0 part /
```

---

# 4 Disabel Transparent Huge Support
1. sudo su
2. echo never > /sys/kernel/mm/transparent_hugepage/enabled
3. echo never > /sys/kernel/mm/transparent_hugepage/defrag
4. sudo vi /etc/rc.d/rc.local
add the lines:
5. echo never > /sys/kernel/mm/transparent_hugepage/enabled
6. echo never > /sys/kernel/mm/transparent_hugepage/defrag


```
ansible all -a 'cat /sys/kernel/mm/transparent_hugepage/enabled'
```

```
172.32.1.87 | CHANGED | rc=0 >>
always madvise [never]

172.32.1.158 | CHANGED | rc=0 >>
always madvise [never]

172.32.1.178 | CHANGED | rc=0 >>
always madvise [never]

172.32.1.171 | CHANGED | rc=0 >>
always madvise [never]

172.32.1.128 | CHANGED | rc=0 >>
always madvise [never]
```


```
ansible all -a 'cat /sys/kernel/mm/transparent_hugepage/defrag
```

```
172.32.1.87 | CHANGED | rc=0 >>
always madvise [never]

172.32.1.178 | CHANGED | rc=0 >>
[always] madvise never

172.32.1.158 | CHANGED | rc=0 >>
always madvise [never]

172.32.1.171 | CHANGED | rc=0 >>
always madvise [never]

172.32.1.128 | CHANGED | rc=0 >>
always madvise [never]

```

```
```

```
```

```
```

```
```
```
```

```
```

```
```

```
```
```
```

```
```

```
```

```
```
