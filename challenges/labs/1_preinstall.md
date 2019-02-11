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
always madvise [never]

172.32.1.158 | CHANGED | rc=0 >>
always madvise [never]

172.32.1.171 | CHANGED | rc=0 >>
always madvise [never]

172.32.1.128 | CHANGED | rc=0 >>
always madvise [never]

```

```
ansible all -a 'cat /etc/rc.d/rc.local'
```

```
172.32.1.87 | CHANGED | rc=0 >>
#!/bin/bash
# THIS FILE IS ADDED FOR COMPATIBILITY PURPOSES
#
# It is highly advisable to create own systemd services or udev rules
# to run scripts during boot instead of using this file.
#
# In contrast to previous versions due to parallel execution during boot
# this script will NOT be run after all other services.
#
# Please note that you must run 'chmod +x /etc/rc.d/rc.local' to ensure
# that this script will be executed during boot.

touch /var/lock/subsys/local
echo never > /sys/kernel/mm/transparent_hugepage/enabled
echo never > /sys/kernel/mm/transparent_hugepage/defrag

172.32.1.178 | CHANGED | rc=0 >>
#!/bin/bash
# THIS FILE IS ADDED FOR COMPATIBILITY PURPOSES
#
# It is highly advisable to create own systemd services or udev rules
# to run scripts during boot instead of using this file.
#
# In contrast to previous versions due to parallel execution during boot
# this script will NOT be run after all other services.
#
# Please note that you must run 'chmod +x /etc/rc.d/rc.local' to ensure
# that this script will be executed during boot.

touch /var/lock/subsys/local
echo never > /sys/kernel/mm/transparent_hugepage/enabled
echo never > /sys/kernel/mm/transparent_hugepage/defrag

172.32.1.128 | CHANGED | rc=0 >>
#!/bin/bash
# THIS FILE IS ADDED FOR COMPATIBILITY PURPOSES
#
# It is highly advisable to create own systemd services or udev rules
# to run scripts during boot instead of using this file.
#
# In contrast to previous versions due to parallel execution during boot
# this script will NOT be run after all other services.
#
# Please note that you must run 'chmod +x /etc/rc.d/rc.local' to ensure
# that this script will be executed during boot.

touch /var/lock/subsys/local
echo never > /sys/kernel/mm/transparent_hugepage/enabled
echo never > /sys/kernel/mm/transparent_hugepage/defrag

172.32.1.171 | CHANGED | rc=0 >>
#!/bin/bash
# THIS FILE IS ADDED FOR COMPATIBILITY PURPOSES
#
# It is highly advisable to create own systemd services or udev rules
# to run scripts during boot instead of using this file.
#
# In contrast to previous versions due to parallel execution during boot
# this script will NOT be run after all other services.
#
# Please note that you must run 'chmod +x /etc/rc.d/rc.local' to ensure
# that this script will be executed during boot.

touch /var/lock/subsys/local
echo never > /sys/kernel/mm/transparent_hugepage/enabled
echo never > /sys/kernel/mm/transparent_hugepage/defrag

172.32.1.158 | CHANGED | rc=0 >>
#!/bin/bash
# THIS FILE IS ADDED FOR COMPATIBILITY PURPOSES
#
# It is highly advisable to create own systemd services or udev rules
# to run scripts during boot instead of using this file.
#
# In contrast to previous versions due to parallel execution during boot
# this script will NOT be run after all other services.
#
# Please note that you must run 'chmod +x /etc/rc.d/rc.local' to ensure
# that this script will be executed during boot.

touch /var/lock/subsys/local
echo never > /sys/kernel/mm/transparent_hugepage/enabled
echo never > /sys/kernel/mm/transparent_hugepage/defrag
```
---

# 5 network interface configuration

## ip-172-32-1-178
```
[ec2-user@ip-172-32-1-178 ~]$ ifconfig -a
eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 9001
        inet 172.32.1.178  netmask 255.255.255.0  broadcast 172.32.1.255
        inet6 fe80::38:98ff:fef4:ba32  prefixlen 64  scopeid 0x20<link>
        ether 02:38:98:f4:ba:32  txqueuelen 1000  (Ethernet)
        RX packets 11849  bytes 9633577 (9.1 MiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 6180  bytes 3160274 (3.0 MiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 1000  (Local Loopback)
        RX packets 34681  bytes 44402385 (42.3 MiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 34681  bytes 44402385 (42.3 MiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

```

## ip-172-32-1-128 
```
[root@ip-172-32-1-128 ec2-user]# ifconfig -a
eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 9001
        inet 172.32.1.128  netmask 255.255.255.0  broadcast 172.32.1.255
        inet6 fe80::e9:87ff:fee2:ca70  prefixlen 64  scopeid 0x20<link>
        ether 02:e9:87:e2:ca:70  txqueuelen 1000  (Ethernet)
        RX packets 4225  bytes 1125541 (1.0 MiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 4339  bytes 515076 (503.0 KiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 1000  (Local Loopback)
        RX packets 797  bytes 667181 (651.5 KiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 797  bytes 667181 (651.5 KiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

```

## ip-172-32-1-171
```
[root@ip-172-32-1-171 ec2-user]# ifconfig -a
eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 9001
        inet 172.32.1.171  netmask 255.255.255.0  broadcast 172.32.1.255
        inet6 fe80::a4:64ff:fe3a:e180  prefixlen 64  scopeid 0x20<link>
        ether 02:a4:64:3a:e1:80  txqueuelen 1000  (Ethernet)
        RX packets 4189  bytes 964754 (942.1 KiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 4287  bytes 534539 (522.0 KiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 1000  (Local Loopback)
        RX packets 753  bytes 607994 (593.7 KiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 753  bytes 607994 (593.7 KiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
```

## ip-172-32-1-87
```
  [root@ip-172-32-1-87 ec2-user]# ifconfig -a
eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 9001
        inet 172.32.1.87  netmask 255.255.255.0  broadcast 172.32.1.255
        inet6 fe80::f2:3ff:fe88:479a  prefixlen 64  scopeid 0x20<link>
        ether 02:f2:03:88:47:9a  txqueuelen 1000  (Ethernet)
        RX packets 4241  bytes 1103706 (1.0 MiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 4335  bytes 533718 (521.2 KiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 1000  (Local Loopback)
        RX packets 762  bytes 660839 (645.3 KiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 762  bytes 660839 (645.3 KiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

```

## ip-172-32-1-158
```
[root@ip-172-32-1-158 ec2-user]# ifconfig -a
eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 9001
        inet 172.32.1.158  netmask 255.255.255.0  broadcast 172.32.1.255
        inet6 fe80::a6:d4ff:fe2c:b88  prefixlen 64  scopeid 0x20<link>
        ether 02:a6:d4:2c:0b:88  txqueuelen 1000  (Ethernet)
        RX packets 5535  bytes 1311524 (1.2 MiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 5626  bytes 673974 (658.1 KiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 1000  (Local Loopback)
        RX packets 1852  bytes 801967 (783.1 KiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 1852  bytes 801967 (783.1 KiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
```

---

# 5 Show that forward and reverse host lookups are correctly resolve

```
ansible all -a 'getent ahosts'
```

```
172.32.1.171 | CHANGED | rc=0 >>
127.0.0.1       localhost localhost.localdomain localhost4 localhost4.localdomain4
127.0.0.1       localhost localhost.localdomain localhost6 localhost6.localdomain6
172.32.1.178    ip-172-32-1-178 d01
172.32.1.128    ip-172-32-1-128 d02
172.32.1.171    ip-172-32-1-171 d03
172.32.1.158    ip-172-32-1-158 d05
172.32.1.87     ip-172-32-1-87 d04

172.32.1.128 | CHANGED | rc=0 >>
127.0.0.1       localhost localhost.localdomain localhost4 localhost4.localdomain4
127.0.0.1       localhost localhost.localdomain localhost6 localhost6.localdomain6
172.32.1.178    ip-172-32-1-178 d01
172.32.1.128    ip-172-32-1-128 d02
172.32.1.171    ip-172-32-1-171 d03
172.32.1.158    ip-172-32-1-158 d05
172.32.1.87     ip-172-32-1-87 d04

172.32.1.87 | CHANGED | rc=0 >>
127.0.0.1       localhost localhost.localdomain localhost4 localhost4.localdomain4
127.0.0.1       localhost localhost.localdomain localhost6 localhost6.localdomain6I
172.32.1.178    ip-172-32-1-178 d01
172.32.1.128    ip-172-32-1-128 d02
172.32.1.171    ip-172-32-1-171 d03
172.32.1.158    ip-172-32-1-158 d05
172.32.1.87     ip-172-32-1-87 d04

172.32.1.178 | CHANGED | rc=0 >>
127.0.0.1       localhost localhost.localdomain localhost4 localhost4.localdomain4
127.0.0.1       localhost localhost.localdomain localhost6 localhost6.localdomain6
172.32.1.178    ip-172-32-1-178 d01
172.32.1.128    ip-172-32-1-128 d02
172.32.1.171    ip-172-32-1-171 d03
172.32.1.158    ip-172-32-1-158 d05
172.32.1.87     ip-172-32-1-87 d04

172.32.1.158 | CHANGED | rc=0 >>
127.0.0.1       localhost localhost.localdomain localhost4 localhost4.localdomain4
127.0.0.1       localhost localhost.localdomain localhost6 localhost6.localdomain6I
172.32.1.178    ip-172-32-1-178 d01
172.32.1.128    ip-172-32-1-128 d02
172.32.1.171    ip-172-32-1-171 d03
172.32.1.158    ip-172-32-1-158 d05
172.32.1.87     ip-172-32-1-87 d04
```

## ip-172-32-1-178
``` 
ansible all -a 'nslookup  172.32.1.178
```

```
172.32.1.171 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
178.1.32.172.in-addr.arpa       name = ip-172-32-1-178.eu-west-1.compute.internal.

Authoritative answers can be found from:

172.32.1.87 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
178.1.32.172.in-addr.arpa       name = ip-172-32-1-178.eu-west-1.compute.internal.

Authoritative answers can be found from:

172.32.1.128 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
178.1.32.172.in-addr.arpa       name = ip-172-32-1-178.eu-west-1.compute.internal.

Authoritative answers can be found from:

172.32.1.158 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
178.1.32.172.in-addr.arpa       name = ip-172-32-1-178.eu-west-1.compute.internal.

Authoritative answers can be found from:

172.32.1.178 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
178.1.32.172.in-addr.arpa       name = ip-172-32-1-178.eu-west-1.compute.internal.

Authoritative answers can be found from:

```

## ip-172-32-1-128
```
ansible all -a 'nslookup  172.32.1.178'
```

```
172.32.1.171 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
178.1.32.172.in-addr.arpa       name = ip-172-32-1-178.eu-west-1.compute.internal.

Authoritative answers can be found from:

172.32.1.87 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
178.1.32.172.in-addr.arpa       name = ip-172-32-1-178.eu-west-1.compute.internal.

Authoritative answers can be found from:

172.32.1.128 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
178.1.32.172.in-addr.arpa       name = ip-172-32-1-178.eu-west-1.compute.internal.

Authoritative answers can be found from:

172.32.1.158 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
178.1.32.172.in-addr.arpa       name = ip-172-32-1-178.eu-west-1.compute.internal.

Authoritative answers can be found from:

172.32.1.178 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
178.1.32.172.in-addr.arpa       name = ip-172-32-1-178.eu-west-1.compute.internal.

Authoritative answers can be found from:

[ec2-user@ip-172-32-1-178 ~]$ ^C
[ec2-user@ip-172-32-1-178 ~]$ ansible all -a 'nslookup  172.32.1.128'
172.32.1.178 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
128.1.32.172.in-addr.arpa       name = ip-172-32-1-128.eu-west-1.compute.internal.

Authoritative answers can be found from:

172.32.1.128 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
128.1.32.172.in-addr.arpa       name = ip-172-32-1-128.eu-west-1.compute.internal.

Authoritative answers can be found from:

172.32.1.158 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
128.1.32.172.in-addr.arpa       name = ip-172-32-1-128.eu-west-1.compute.internal.

Authoritative answers can be found from:

172.32.1.87 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
128.1.32.172.in-addr.arpa       name = ip-172-32-1-128.eu-west-1.compute.internal.

Authoritative answers can be found from:

172.32.1.171 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
128.1.32.172.in-addr.arpa       name = ip-172-32-1-128.eu-west-1.compute.internal.

Authoritative answers can be found from:

```

## ip-172-32-1-171
```
ansible all -a 'nslookup  172.32.1.128'
```

```
172.32.1.178 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
128.1.32.172.in-addr.arpa       name = ip-172-32-1-128.eu-west-1.compute.internal.

Authoritative answers can be found from:

172.32.1.128 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
128.1.32.172.in-addr.arpa       name = ip-172-32-1-128.eu-west-1.compute.internal.

Authoritative answers can be found from:

172.32.1.158 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
128.1.32.172.in-addr.arpa       name = ip-172-32-1-128.eu-west-1.compute.internal.

Authoritative answers can be found from:

172.32.1.87 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
128.1.32.172.in-addr.arpa       name = ip-172-32-1-128.eu-west-1.compute.internal.

Authoritative answers can be found from:

172.32.1.171 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
128.1.32.172.in-addr.arpa       name = ip-172-32-1-128.eu-west-1.compute.internal.

Authoritative answers can be found from:

[ec2-user@ip-172-32-1-178 ~]$ ansible all -a 'nslookup  172.32.1.171'
172.32.1.128 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
171.1.32.172.in-addr.arpa       name = ip-172-32-1-171.eu-west-1.compute.internal.

Authoritative answers can be found from:

172.32.1.178 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
171.1.32.172.in-addr.arpa       name = ip-172-32-1-171.eu-west-1.compute.internal.

Authoritative answers can be found from:

172.32.1.87 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
171.1.32.172.in-addr.arpa       name = ip-172-32-1-171.eu-west-1.compute.internal.

Authoritative answers can be found from:

172.32.1.171 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
171.1.32.172.in-addr.arpa       name = ip-172-32-1-171.eu-west-1.compute.internal.

Authoritative answers can be found from:

172.32.1.158 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
171.1.32.172.in-addr.arpa       name = ip-172-32-1-171.eu-west-1.compute.internal.

Authoritative answers can be found from:

```


## ip-172-32-1-158
```
ansible all -a 'nslookup  172.32.1.158'
```

```
172.32.1.87 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
158.1.32.172.in-addr.arpa       name = ip-172-32-1-158.eu-west-1.compute.internal.

Authoritative answers can be found from:

172.32.1.178 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
158.1.32.172.in-addr.arpa       name = ip-172-32-1-158.eu-west-1.compute.internal.

Authoritative answers can be found from:

172.32.1.171 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
158.1.32.172.in-addr.arpa       name = ip-172-32-1-158.eu-west-1.compute.internal.

Authoritative answers can be found from:

172.32.1.128 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
158.1.32.172.in-addr.arpa       name = ip-172-32-1-158.eu-west-1.compute.internal.

Authoritative answers can be found from:

172.32.1.158 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
158.1.32.172.in-addr.arpa       name = ip-172-32-1-158.eu-west-1.compute.internal.

Authoritative answers can be found from:

```


## ip-172-32-1-87
```
 ansible all -a 'nslookup  172.32.1.187'
```

```
172.32.1.178 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
187.1.32.172.in-addr.arpa       name = ip-172-32-1-187.eu-west-1.compute.internal.

Authoritative answers can be found from:

172.32.1.128 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
187.1.32.172.in-addr.arpa       name = ip-172-32-1-187.eu-west-1.compute.internal.

Authoritative answers can be found from:

172.32.1.87 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
187.1.32.172.in-addr.arpa       name = ip-172-32-1-187.eu-west-1.compute.internal.

Authoritative answers can be found from:

172.32.1.171 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
187.1.32.172.in-addr.arpa       name = ip-172-32-1-187.eu-west-1.compute.internal.

Authoritative answers can be found from:

172.32.1.158 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
187.1.32.172.in-addr.arpa       name = ip-172-32-1-187.eu-west-1.compute.internal.

Authoritative answers can be found from:

```

