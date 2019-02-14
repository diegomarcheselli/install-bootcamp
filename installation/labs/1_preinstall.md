#  CDH Cluster Installation v 5.15.2

---



## Allow SSH Password less from Master Node to Slave Node

1. Create Public Key: ssh-keygen -> this create a file with private key and another with public key: id_rsa.pub
2. copy the content of id_rsa.pub inside authorized_keys of every other node
3. Append id_rsa.pub to .ssh/authorized_keys: cat .ssh/id_rsa.pub >> .ssh/authorized_keys in ea



## Update yum and Install utility software:

1. sudo yum update
2. sudo yum install wget
on each node 



## Ansible host file 

```
[cluster]
172.32.1.224
172.32.1.206
172.32.1.137
172.32.1.56
172.32.1.38

[slaves]
172.32.1.206
172.32.1.137
172.32.1.56
172.32.1.38
```


## Linux release 

```
ansible all -a 'cat /etc/redhat-release'
```

```
172.32.1.56 | CHANGED | rc=0 >>
Red Hat Enterprise Linux Server release 7.6 (Maipo)

172.32.1.206 | CHANGED | rc=0 >>
Red Hat Enterprise Linux Server release 7.6 (Maipo)

172.32.1.137 | CHANGED | rc=0 >>
Red Hat Enterprise Linux Server release 7.6 (Maipo)

172.32.1.38 | CHANGED | rc=0 >>
Red Hat Enterprise Linux Server release 7.6 (Maipo)

172.32.1.224 | CHANGED | rc=0 >>
Red Hat Enterprise Linux Server release 7.6 (Maipo)

```



## Configure Network Names

```
ansible cluster -a 'hostname -f'
```

```
172.32.1.137 | CHANGED | rc=0 >>
ip-172-32-1-137

172.32.1.38 | CHANGED | rc=0 >>
ip-172-32-1-38

172.32.1.56 | CHANGED | rc=0 >>
ip-172-32-1-56

172.32.1.206 | CHANGED | rc=0 >>
ip-172-32-1-206

172.32.1.224 | CHANGED | rc=0 >>
ip-172-32-1-224

```



## 1 swappines

```
ansible all -a 'sudo  sysctl -w vm.swappiness=1'
and
sudo bash -c "echo 'vm.swappiness = 1' >> /etc/sysctl.conf"
on each node 
```

```
172.32.1.38 | CHANGED | rc=0 >>
vm.swappiness = 1

172.32.1.56 | CHANGED | rc=0 >>
vm.swappiness = 1

172.32.1.206 | CHANGED | rc=0 >>
vm.swappiness = 1

172.32.1.137 | CHANGED | rc=0 >>
vm.swappiness = 1

172.32.1.224 | CHANGED | rc=0 >>
vm.swappiness = 1

```



## 2 Volume Attributes

```
ansible all -a 'df -h'
```

```
172.32.1.38 | CHANGED | rc=0 >>
Filesystem      Size  Used Avail Use% Mounted on
/dev/nvme0n1p2   50G  9.1G   41G  19% /
devtmpfs        7.6G     0  7.6G   0% /dev
tmpfs           7.6G     0  7.6G   0% /dev/shm
tmpfs           7.6G  8.6M  7.6G   1% /run
tmpfs           7.6G     0  7.6G   0% /sys/fs/cgroup
tmpfs           1.6G     0  1.6G   0% /run/user/0
cm_processes    7.6G  1.6M  7.6G   1% /run/cloudera-scm-agent/process
tmpfs           1.6G     0  1.6G   0% /run/user/1000

172.32.1.137 | CHANGED | rc=0 >>
Filesystem      Size  Used Avail Use% Mounted on
/dev/nvme0n1p2   50G  9.1G   41G  19% /
devtmpfs        7.6G     0  7.6G   0% /dev
tmpfs           7.6G     0  7.6G   0% /dev/shm
tmpfs           7.6G  8.6M  7.6G   1% /run
tmpfs           7.6G     0  7.6G   0% /sys/fs/cgroup
tmpfs           1.6G     0  1.6G   0% /run/user/0
cm_processes    7.6G   14M  7.6G   1% /run/cloudera-scm-agent/process
tmpfs           1.6G     0  1.6G   0% /run/user/1000

172.32.1.206 | CHANGED | rc=0 >>
Filesystem      Size  Used Avail Use% Mounted on
/dev/nvme0n1p2   50G   11G   40G  22% /
devtmpfs        7.6G     0  7.6G   0% /dev
tmpfs           7.6G     0  7.6G   0% /dev/shm
tmpfs           7.6G  8.6M  7.6G   1% /run
tmpfs           7.6G     0  7.6G   0% /sys/fs/cgroup
tmpfs           1.6G     0  1.6G   0% /run/user/0
cm_processes    7.6G  1.7M  7.6G   1% /run/cloudera-scm-agent/process
tmpfs           1.6G     0  1.6G   0% /run/user/1000

172.32.1.56 | CHANGED | rc=0 >>
Filesystem      Size  Used Avail Use% Mounted on
/dev/nvme0n1p2   50G  9.1G   41G  19% /
devtmpfs        7.6G     0  7.6G   0% /dev
tmpfs           7.6G     0  7.6G   0% /dev/shm
tmpfs           7.6G  8.6M  7.6G   1% /run
tmpfs           7.6G     0  7.6G   0% /sys/fs/cgroup
tmpfs           1.6G     0  1.6G   0% /run/user/0
cm_processes    7.6G  1.6M  7.6G   1% /run/cloudera-scm-agent/process
tmpfs           1.6G     0  1.6G   0% /run/user/1000

172.32.1.224 | CHANGED | rc=0 >>
Filesystem      Size  Used Avail Use% Mounted on
/dev/nvme0n1p2   50G   33G   18G  65% /
devtmpfs        7.6G     0  7.6G   0% /dev
tmpfs           7.6G  124K  7.6G   1% /dev/shm
tmpfs           7.6G  8.7M  7.6G   1% /run
tmpfs           7.6G     0  7.6G   0% /sys/fs/cgroup
tmpfs           1.6G     0  1.6G   0% /run/user/0
tmpfs           1.6G     0  1.6G   0% /run/user/997
cm_processes    7.6G  1.7M  7.6G   1% /run/cloudera-scm-agent/process
tmpfs           1.6G     0  1.6G   0% /run/user/1000

```

```
ansible all -a 'lsblk'
```

```
172.32.1.38 | CHANGED | rc=0 >>
NAME        MAJ:MIN RM SIZE RO TYPE MOUNTPOINT
nvme0n1     259:0    0  50G  0 disk
├─nvme0n1p1 259:1    0   1M  0 part
└─nvme0n1p2 259:2    0  50G  0 part /

172.32.1.137 | CHANGED | rc=0 >>
NAME        MAJ:MIN RM SIZE RO TYPE MOUNTPOINT
nvme0n1     259:0    0  50G  0 disk
├─nvme0n1p1 259:1    0   1M  0 part
└─nvme0n1p2 259:2    0  50G  0 part /

172.32.1.56 | CHANGED | rc=0 >>
NAME        MAJ:MIN RM SIZE RO TYPE MOUNTPOINT
nvme0n1     259:0    0  50G  0 disk
├─nvme0n1p1 259:1    0   1M  0 part
└─nvme0n1p2 259:2    0  50G  0 part /

172.32.1.206 | CHANGED | rc=0 >>
NAME        MAJ:MIN RM SIZE RO TYPE MOUNTPOINT
nvme0n1     259:0    0  50G  0 disk
├─nvme0n1p1 259:1    0   1M  0 part
└─nvme0n1p2 259:2    0  50G  0 part /

172.32.1.224 | CHANGED | rc=0 >>
NAME        MAJ:MIN RM SIZE RO TYPE MOUNTPOINT
nvme0n1     259:0    0  50G  0 disk
├─nvme0n1p1 259:1    0   1M  0 part
└─nvme0n1p2 259:2    0  50G  0 part /
```



## Disable SELinux

for each node
1. sudo setenforce 0
2. sudo vi  /etc/selinux/config
	set SELINUX=disabled

```
ansible all -a 'sudo cat /etc/selinux/config'
```

```
172.32.1.56 | CHANGED | rc=0 >>

# This file controls the state of SELinux on the system.
# SELINUX= can take one of these three values:
#     enforcing - SELinux security policy is enforced.
#     permissive - SELinux prints warnings instead of enforcing.
#     disabled - No SELinux policy is loaded.
SELINUX=disabled
# SELINUXTYPE= can take one of three values:
#     targeted - Targeted processes are protected,
#     minimum - Modification of targeted policy. Only selected processes are protected.
#     mls - Multi Level Security protection.
SELINUXTYPE=targeted

172.32.1.137 | CHANGED | rc=0 >>

# This file controls the state of SELinux on the system.
# SELINUX= can take one of these three values:
#     enforcing - SELinux security policy is enforced.
#     permissive - SELinux prints warnings instead of enforcing.
#     disabled - No SELinux policy is loaded.
SELINUX=disabled
# SELINUXTYPE= can take one of three values:
#     targeted - Targeted processes are protected,
#     minimum - Modification of targeted policy. Only selected processes are protected.
#     mls - Multi Level Security protection.
SELINUXTYPE=targeted

172.32.1.38 | CHANGED | rc=0 >>

# This file controls the state of SELinux on the system.
# SELINUX= can take one of these three values:
#     enforcing - SELinux security policy is enforced.
#     permissive - SELinux prints warnings instead of enforcing.
#     disabled - No SELinux policy is loaded.
SELINUX=disabled
# SELINUXTYPE= can take one of three values:
#     targeted - Targeted processes are protected,
#     minimum - Modification of targeted policy. Only selected processes are protected.
#     mls - Multi Level Security protection.
SELINUXTYPE=targeted

172.32.1.206 | CHANGED | rc=0 >>

# This file controls the state of SELinux on the system.
# SELINUX= can take one of these three values:
#     enforcing - SELinux security policy is enforced.
#     permissive - SELinux prints warnings instead of enforcing.
#     disabled - No SELinux policy is loaded.
SELINUX=disabled
# SELINUXTYPE= can take one of three values:
#     targeted - Targeted processes are protected,
#     minimum - Modification of targeted policy. Only selected processes are protected.
#     mls - Multi Level Security protection.
SELINUXTYPE=targeted

172.32.1.224 | CHANGED | rc=0 >>

# This file controls the state of SELinux on the system.
# SELINUX= can take one of these three values:
#     enforcing - SELinux security policy is enforced.
#     permissive - SELinux prints warnings instead of enforcing.
#     disabled - No SELinux policy is loaded.
SELINUX=disabled
# SELINUXTYPE= can take one of three values:
#     targeted - Targeted processes are protected,
#     minimum - Modification of targeted policy. Only selected processes are protected.
#     mls - Multi Level Security protection.
SELINUXTYPE=targeted
```



##  4 Disable Transparent Huge Support

on each node:
1. sudo su
2. echo never > /sys/kernel/mm/transparent_hugepage/enabled
3. echo never > /sys/kernel/mm/transparent_hugepage/defrag


4. 'echo never > /sys/kernel/mm/transparent_hugepage/enabled' >> /etc/rc.d/rc.local
5. 'echo never > /sys/kernel/mm/transparent_hugepage/defrag' >> /etc/rc.d/rc.local

```
 ansible all -a 'sudo cat /sys/kernel/mm/transparent_hugepage/enabled'
```

```
172.32.1.137 | CHANGED | rc=0 >>
always madvise [never]

172.32.1.206 | CHANGED | rc=0 >>
always madvise [never]

172.32.1.56 | CHANGED | rc=0 >>
always madvise [never]

172.32.1.224 | CHANGED | rc=0 >>
always madvise [never]

172.32.1.38 | CHANGED | rc=0 >>
always madvise [never]
```


```
 ansible all -a 'sudo cat /sys/kernel/mm/transparent_hugepage/defrag'
```

```
172.32.1.56 | CHANGED | rc=0 >>
always madvise [never]

172.32.1.137 | CHANGED | rc=0 >>
always madvise [never]

172.32.1.206 | CHANGED | rc=0 >>
always madvise [never]

172.32.1.38 | CHANGED | rc=0 >>
always madvise [never]

172.32.1.224 | CHANGED | rc=0 >>
always madvise [never]
```



## 5 Network interface configuration

```
ansible all -a 'sudo ifconfig -a'
```

```
172.32.1.38 | CHANGED | rc=0 >>
eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 9001
        inet 172.32.1.38  netmask 255.255.255.0  broadcast 172.32.1.255
        inet6 fe80::72:79ff:fe2d:712a  prefixlen 64  scopeid 0x20<link>
        ether 02:72:79:2d:71:2a  txqueuelen 1000  (Ethernet)
        RX packets 24033  bytes 4289818 (4.0 MiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 40765  bytes 8774960 (8.3 MiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 1000  (Local Loopback)
        RX packets 22484  bytes 63704323 (60.7 MiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 22484  bytes 63704323 (60.7 MiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

172.32.1.137 | CHANGED | rc=0 >>
eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 9001
        inet 172.32.1.137  netmask 255.255.255.0  broadcast 172.32.1.255
        inet6 fe80::cb:f7ff:fe78:e4fa  prefixlen 64  scopeid 0x20<link>
        ether 02:cb:f7:78:e4:fa  txqueuelen 1000  (Ethernet)
        RX packets 379493  bytes 300598304 (286.6 MiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 324720  bytes 61071768 (58.2 MiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 1000  (Local Loopback)
        RX packets 193629  bytes 249630026 (238.0 MiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 193629  bytes 249630026 (238.0 MiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

172.32.1.56 | CHANGED | rc=0 >>
eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 9001
        inet 172.32.1.56  netmask 255.255.255.0  broadcast 172.32.1.255
        inet6 fe80::f1:a2ff:fe27:247c  prefixlen 64  scopeid 0x20<link>
        ether 02:f1:a2:27:24:7c  txqueuelen 1000  (Ethernet)
        RX packets 24118  bytes 4375061 (4.1 MiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 40851  bytes 8839995 (8.4 MiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 1000  (Local Loopback)
        RX packets 22593  bytes 64308119 (61.3 MiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 22593  bytes 64308119 (61.3 MiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

172.32.1.224 | CHANGED | rc=0 >>
eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 9001
        inet 172.32.1.224  netmask 255.255.255.0  broadcast 172.32.1.255
        inet6 fe80::66:f7ff:fe05:cb54  prefixlen 64  scopeid 0x20<link>
        ether 02:66:f7:05:cb:54  txqueuelen 1000  (Ethernet)
        RX packets 15997834  bytes 22037770519 (20.5 GiB)
        RX errors 0  dropped 291  overruns 0  frame 0
        TX packets 3531147  bytes 504197563 (480.8 MiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 1000  (Local Loopback)
        RX packets 502843  bytes 1026401862 (978.8 MiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 502843  bytes 1026401862 (978.8 MiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

172.32.1.206 | CHANGED | rc=0 >>
eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 9001
        inet 172.32.1.206  netmask 255.255.255.0  broadcast 172.32.1.255
        inet6 fe80::64:21ff:fe95:5ea  prefixlen 64  scopeid 0x20<link>
        ether 02:64:21:95:05:ea  txqueuelen 1000  (Ethernet)
        RX packets 66044  bytes 8983525 (8.5 MiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 71359  bytes 15116978 (14.4 MiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 1000  (Local Loopback)
        RX packets 23385  bytes 64877582 (61.8 MiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 23385  bytes 64877582 (61.8 MiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
```



## Show that forward and reverse host lookups are correctly resolve

### getent
```
ansible all -a 'getent ahosts'
```

```
172.32.1.137 | CHANGED | rc=0 >>
127.0.0.1       localhost localhost.localdomain localhost4 localhost4.localdomain4
127.0.0.1       localhost localhost.localdomain localhost6 localhost6.localdomain6
172.32.1.224    ip-172-32-1-224 d01
172.32.1.206    ip-172-32-1-206 d02
172.32.1.137    ip-172-32-1-137 d03
172.32.1.56     ip-172-32-1-56 d04
172.32.1.38     ip-172-32-1-38 d05

172.32.1.56 | CHANGED | rc=0 >>
127.0.0.1       localhost localhost.localdomain localhost4 localhost4.localdomain4
127.0.0.1       localhost localhost.localdomain localhost6 localhost6.localdomain6
172.32.1.224    ip-172-32-1-224 d01
172.32.1.206    ip-172-32-1-206 d02
172.32.1.137    ip-172-32-1-137 d03
172.32.1.56     ip-172-32-1-56 d04
172.32.1.38     ip-172-32-1-38 d05

172.32.1.206 | CHANGED | rc=0 >>
127.0.0.1       localhost localhost.localdomain localhost4 localhost4.localdomain4
127.0.0.1       localhost localhost.localdomain localhost6 localhost6.localdomain6
172.32.1.224    ip-172-32-1-224 d01
172.32.1.206    ip-172-32-1-206 d02
172.32.1.137    ip-172-32-1-137 d03
172.32.1.56     ip-172-32-1-56 d04
172.32.1.38     ip-172-32-1-38 d05

172.32.1.224 | CHANGED | rc=0 >>
127.0.0.1       localhost localhost.localdomain localhost4 localhost4.localdomain4
127.0.0.1       localhost localhost.localdomain localhost6 localhost6.localdomain6
172.32.1.224    ip-172-32-1-224 d01
172.32.1.206    ip-172-32-1-206 d02
172.32.1.137    ip-172-32-1-137 d03
172.32.1.56     ip-172-32-1-56 d04
172.32.1.38     ip-172-32-1-38 d05

172.32.1.38 | CHANGED | rc=0 >>
127.0.0.1       localhost localhost.localdomain localhost4 localhost4.localdomain4
127.0.0.1       localhost localhost.localdomain localhost6 localhost6.localdomain6
172.32.1.224    ip-172-32-1-224 d01
172.32.1.206    ip-172-32-1-206 d02
172.32.1.137    ip-172-32-1-137 d03
172.32.1.56     ip-172-32-1-56 d04
172.32.1.38     ip-172-32-1-38 d05
```

### nlookup

```
ansible all -a 'nslookup  172.32.1.224'
```

```
172.32.1.206 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
224.1.32.172.in-addr.arpa       name = ip-172-32-1-224.eu-west-1.compute.internal.

Authoritative answers can be found from:

172.32.1.38 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
224.1.32.172.in-addr.arpa       name = ip-172-32-1-224.eu-west-1.compute.internal.

Authoritative answers can be found from:

172.32.1.137 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
224.1.32.172.in-addr.arpa       name = ip-172-32-1-224.eu-west-1.compute.internal.

Authoritative answers can be found from:

172.32.1.224 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
224.1.32.172.in-addr.arpa       name = ip-172-32-1-224.eu-west-1.compute.internal.

Authoritative answers can be found from:

172.32.1.56 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
224.1.32.172.in-addr.arpa       name = ip-172-32-1-224.eu-west-1.compute.internal.

Authoritative answers can be found from:
```



```
ansible all -a 'nslookup  172.32.1.206'
```



```
172.32.1.137 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
206.1.32.172.in-addr.arpa       name = ip-172-32-1-206.eu-west-1.compute.internal.

Authoritative answers can be found from:

172.32.1.38 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
206.1.32.172.in-addr.arpa       name = ip-172-32-1-206.eu-west-1.compute.internal.

Authoritative answers can be found from:

172.32.1.56 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
206.1.32.172.in-addr.arpa       name = ip-172-32-1-206.eu-west-1.compute.internal.

Authoritative answers can be found from:

172.32.1.224 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
206.1.32.172.in-addr.arpa       name = ip-172-32-1-206.eu-west-1.compute.internal.

Authoritative answers can be found from:

172.32.1.206 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
206.1.32.172.in-addr.arpa       name = ip-172-32-1-206.eu-west-1.compute.internal.
```


```
 ansible all -a 'nslookup  172.32.1.137'
```

```
172.32.1.224 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
137.1.32.172.in-addr.arpa       name = ip-172-32-1-137.eu-west-1.compute.internal.

Authoritative answers can be found from:

172.32.1.56 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
137.1.32.172.in-addr.arpa       name = ip-172-32-1-137.eu-west-1.compute.internal.

Authoritative answers can be found from:

172.32.1.38 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
137.1.32.172.in-addr.arpa       name = ip-172-32-1-137.eu-west-1.compute.internal.

Authoritative answers can be found from:

172.32.1.206 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
137.1.32.172.in-addr.arpa       name = ip-172-32-1-137.eu-west-1.compute.internal.

Authoritative answers can be found from:

172.32.1.137 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
137.1.32.172.in-addr.arpa       name = ip-172-32-1-137.eu-west-1.compute.internal.

Authoritative answers can be found from:
```



```
ansible all -a 'nslookup  172.32.1.56'
```



```
172.32.1.56 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
56.1.32.172.in-addr.arpa        name = ip-172-32-1-56.eu-west-1.compute.internal.

Authoritative answers can be found from:

172.32.1.224 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
56.1.32.172.in-addr.arpa        name = ip-172-32-1-56.eu-west-1.compute.internal.

Authoritative answers can be found from:

172.32.1.137 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
56.1.32.172.in-addr.arpa        name = ip-172-32-1-56.eu-west-1.compute.internal.

Authoritative answers can be found from:

172.32.1.206 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
56.1.32.172.in-addr.arpa        name = ip-172-32-1-56.eu-west-1.compute.internal.

Authoritative answers can be found from:

172.32.1.38 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
56.1.32.172.in-addr.arpa        name = ip-172-32-1-56.eu-west-1.compute.internal.

Authoritative answers can be found from:

```



```
 ansible all -a 'nslookup  172.32.1.38'
```



```
172.32.1.38 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
38.1.32.172.in-addr.arpa        name = ip-172-32-1-38.eu-west-1.compute.internal.

Authoritative answers can be found from:

172.32.1.224 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
38.1.32.172.in-addr.arpa        name = ip-172-32-1-38.eu-west-1.compute.internal.

Authoritative answers can be found from:

172.32.1.137 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
38.1.32.172.in-addr.arpa        name = ip-172-32-1-38.eu-west-1.compute.internal.

Authoritative answers can be found from:

172.32.1.56 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
38.1.32.172.in-addr.arpa        name = ip-172-32-1-38.eu-west-1.compute.internal.

Authoritative answers can be found from:

172.32.1.206 | CHANGED | rc=0 >>
Server:         169.254.169.253
Address:        169.254.169.253#53

Non-authoritative answer:
38.1.32.172.in-addr.arpa        name = ip-172-32-1-38.eu-west-1.compute.internal.

Authoritative answers can be found from:
```



## 6 nscd service is running


```
ansible all -a 'sudo systemctl status nscd'
```

```
172.32.1.224 | CHANGED | rc=0 >>
● nscd.service - Name Service Cache Daemon
   Loaded: loaded (/usr/lib/systemd/system/nscd.service; enabled; vendor preset: disabled)
   Active: active (running) since Tue 2019-02-12 12:24:49 UTC; 1min 41s ago
 Main PID: 1072 (nscd)
   CGroup: /system.slice/nscd.service
           └─1072 /usr/sbin/nscd

Feb 12 12:24:49 ip-172-32-1-224 nscd[1072]: 1072 monitoring file `/etc/hosts` (4)
Feb 12 12:24:49 ip-172-32-1-224 nscd[1072]: 1072 monitoring directory `/etc` (2)
Feb 12 12:24:49 ip-172-32-1-224 nscd[1072]: 1072 monitoring file `/etc/resolv.conf` (5)
Feb 12 12:24:49 ip-172-32-1-224 nscd[1072]: 1072 monitoring directory `/etc` (2)
Feb 12 12:24:49 ip-172-32-1-224 nscd[1072]: 1072 monitoring file `/etc/services` (6)
Feb 12 12:24:49 ip-172-32-1-224 nscd[1072]: 1072 monitoring directory `/etc` (2)
Feb 12 12:24:49 ip-172-32-1-224 nscd[1072]: 1072 disabled inotify-based monitoring for file `/etc/netgroup': No such file or directory
Feb 12 12:24:49 ip-172-32-1-224 nscd[1072]: 1072 stat failed for file `/etc/netgroup'; will try again later: No such file or directory
Feb 12 12:24:49 ip-172-32-1-224 systemd[1]: Started Name Service Cache Daemon.
Feb 12 12:25:08 ip-172-32-1-224 nscd[1072]: 1072 checking for monitored file `/etc/netgroup': No such file or directory

172.32.1.38 | CHANGED | rc=0 >>
● nscd.service - Name Service Cache Daemon
   Loaded: loaded (/usr/lib/systemd/system/nscd.service; enabled; vendor preset: disabled)
   Active: active (running) since Tue 2019-02-12 12:25:32 UTC; 58s ago
 Main PID: 29039 (nscd)
   CGroup: /system.slice/nscd.service
           └─29039 /usr/sbin/nscd

Feb 12 12:25:32 ip-172-32-1-38 nscd[29039]: 29039 monitoring file `/etc/hosts` (4)
Feb 12 12:25:32 ip-172-32-1-38 nscd[29039]: 29039 monitoring directory `/etc` (2)
Feb 12 12:25:32 ip-172-32-1-38 nscd[29039]: 29039 monitoring file `/etc/resolv.conf` (5)
Feb 12 12:25:32 ip-172-32-1-38 nscd[29039]: 29039 monitoring directory `/etc` (2)
Feb 12 12:25:32 ip-172-32-1-38 nscd[29039]: 29039 monitoring file `/etc/services` (6)
Feb 12 12:25:32 ip-172-32-1-38 nscd[29039]: 29039 monitoring directory `/etc` (2)
Feb 12 12:25:32 ip-172-32-1-38 nscd[29039]: 29039 disabled inotify-based monitoring for file `/etc/netgroup': No such file or directory
Feb 12 12:25:32 ip-172-32-1-38 nscd[29039]: 29039 stat failed for file `/etc/netgroup'; will try again later: No such file or directory
Feb 12 12:25:32 ip-172-32-1-38 systemd[1]: Started Name Service Cache Daemon.
Feb 12 12:25:51 ip-172-32-1-38 nscd[29039]: 29039 checking for monitored file `/etc/netgroup': No such file or directory

172.32.1.206 | CHANGED | rc=0 >>
● nscd.service - Name Service Cache Daemon
   Loaded: loaded (/usr/lib/systemd/system/nscd.service; enabled; vendor preset: disabled)
   Active: active (running) since Tue 2019-02-12 12:25:14 UTC; 1min 15s ago
 Main PID: 30603 (nscd)
   CGroup: /system.slice/nscd.service
           └─30603 /usr/sbin/nscd

Feb 12 12:25:14 ip-172-32-1-206 nscd[30603]: 30603 monitoring file `/etc/hosts` (4)
Feb 12 12:25:14 ip-172-32-1-206 nscd[30603]: 30603 monitoring directory `/etc` (2)
Feb 12 12:25:14 ip-172-32-1-206 nscd[30603]: 30603 monitoring file `/etc/resolv.conf` (5)
Feb 12 12:25:14 ip-172-32-1-206 nscd[30603]: 30603 monitoring directory `/etc` (2)
Feb 12 12:25:14 ip-172-32-1-206 nscd[30603]: 30603 monitoring file `/etc/services` (6)
Feb 12 12:25:14 ip-172-32-1-206 nscd[30603]: 30603 monitoring directory `/etc` (2)
Feb 12 12:25:14 ip-172-32-1-206 nscd[30603]: 30603 disabled inotify-based monitoring for file `/etc/netgroup': No such file or directory
Feb 12 12:25:14 ip-172-32-1-206 nscd[30603]: 30603 stat failed for file `/etc/netgroup'; will try again later: No such file or directory
Feb 12 12:25:14 ip-172-32-1-206 systemd[1]: Started Name Service Cache Daemon.
Feb 12 12:25:33 ip-172-32-1-206 nscd[30603]: 30603 checking for monitored file `/etc/netgroup': No such file or directory

172.32.1.56 | CHANGED | rc=0 >>
● nscd.service - Name Service Cache Daemon
   Loaded: loaded (/usr/lib/systemd/system/nscd.service; enabled; vendor preset: disabled)
   Active: active (running) since Tue 2019-02-12 12:25:28 UTC; 1min 1s ago
 Main PID: 29712 (nscd)
   CGroup: /system.slice/nscd.service
           └─29712 /usr/sbin/nscd

Feb 12 12:25:28 ip-172-32-1-56 nscd[29712]: 29712 monitoring file `/etc/hosts` (4)
Feb 12 12:25:28 ip-172-32-1-56 nscd[29712]: 29712 monitoring directory `/etc` (2)
Feb 12 12:25:28 ip-172-32-1-56 nscd[29712]: 29712 monitoring file `/etc/resolv.conf` (5)
Feb 12 12:25:28 ip-172-32-1-56 nscd[29712]: 29712 monitoring directory `/etc` (2)
Feb 12 12:25:28 ip-172-32-1-56 nscd[29712]: 29712 monitoring file `/etc/services` (6)
Feb 12 12:25:28 ip-172-32-1-56 nscd[29712]: 29712 monitoring directory `/etc` (2)
Feb 12 12:25:28 ip-172-32-1-56 nscd[29712]: 29712 disabled inotify-based monitoring for file `/etc/netgroup': No such file or directory
Feb 12 12:25:28 ip-172-32-1-56 nscd[29712]: 29712 stat failed for file `/etc/netgroup'; will try again later: No such file or directory
Feb 12 12:25:28 ip-172-32-1-56 systemd[1]: Started Name Service Cache Daemon.
Feb 12 12:25:47 ip-172-32-1-56 nscd[29712]: 29712 checking for monitored file `/etc/netgroup': No such file or directory

172.32.1.137 | CHANGED | rc=0 >>
● nscd.service - Name Service Cache Daemon
   Loaded: loaded (/usr/lib/systemd/system/nscd.service; enabled; vendor preset: disabled)
   Active: active (running) since Tue 2019-02-12 12:25:20 UTC; 1min 10s ago
 Main PID: 14749 (nscd)
   CGroup: /system.slice/nscd.service
           └─14749 /usr/sbin/nscd

Feb 12 12:25:20 ip-172-32-1-137 nscd[14749]: 14749 monitoring file `/etc/hosts` (4)
Feb 12 12:25:20 ip-172-32-1-137 nscd[14749]: 14749 monitoring directory `/etc` (2)
Feb 12 12:25:20 ip-172-32-1-137 nscd[14749]: 14749 monitoring file `/etc/resolv.conf` (5)
Feb 12 12:25:20 ip-172-32-1-137 nscd[14749]: 14749 monitoring directory `/etc` (2)
Feb 12 12:25:20 ip-172-32-1-137 nscd[14749]: 14749 monitoring file `/etc/services` (6)
Feb 12 12:25:20 ip-172-32-1-137 nscd[14749]: 14749 monitoring directory `/etc` (2)
Feb 12 12:25:20 ip-172-32-1-137 nscd[14749]: 14749 disabled inotify-based monitoring for file `/etc/netgroup': No such file or directory
Feb 12 12:25:20 ip-172-32-1-137 nscd[14749]: 14749 stat failed for file `/etc/netgroup'; will try again later: No such file or directory
Feb 12 12:25:20 ip-172-32-1-137 systemd[1]: Started Name Service Cache Daemon.
Feb 12 12:25:39 ip-172-32-1-137 nscd[14749]: 14749 checking for monitored file `/etc/netgroup': No such file or directory
```



## 7 ntpd service is running


```
 ansible all -a 'sudo systemctl status ntpd'
```



```
172.32.1.38 | CHANGED | rc=0 >>
● ntpd.service - Network Time Service
   Loaded: loaded (/usr/lib/systemd/system/ntpd.service; enabled; vendor preset: disabled)
   Active: active (running) since Tue 2019-02-12 12:54:10 UTC; 37s ago
 Main PID: 31269 (ntpd)
   CGroup: /system.slice/ntpd.service
           └─31269 /usr/sbin/ntpd -u ntp:ntp -g

Feb 12 12:54:10 ip-172-32-1-38 ntpd[31269]: Listen and drop on 0 v4wildcard 0.0.0.0 UDP 123
Feb 12 12:54:10 ip-172-32-1-38 ntpd[31269]: Listen and drop on 1 v6wildcard :: UDP 123
Feb 12 12:54:10 ip-172-32-1-38 ntpd[31269]: Listen normally on 2 lo 127.0.0.1 UDP 123
Feb 12 12:54:10 ip-172-32-1-38 ntpd[31269]: Listen normally on 3 eth0 172.32.1.38 UDP 123
Feb 12 12:54:10 ip-172-32-1-38 ntpd[31269]: Listen normally on 4 lo ::1 UDP 123
Feb 12 12:54:10 ip-172-32-1-38 ntpd[31269]: Listen normally on 5 eth0 fe80::72:79ff:fe2d:712a UDP 123
Feb 12 12:54:10 ip-172-32-1-38 ntpd[31269]: Listening on routing socket on fd #22 for interface updates
Feb 12 12:54:10 ip-172-32-1-38 ntpd[31269]: 0.0.0.0 c016 06 restart
Feb 12 12:54:10 ip-172-32-1-38 ntpd[31269]: 0.0.0.0 c012 02 freq_set kernel 5.609 PPM
Feb 12 12:54:17 ip-172-32-1-38 ntpd[31269]: 0.0.0.0 c615 05 clock_sync

172.32.1.137 | CHANGED | rc=0 >>
● ntpd.service - Network Time Service
   Loaded: loaded (/usr/lib/systemd/system/ntpd.service; enabled; vendor preset: disabled)
   Active: active (running) since Tue 2019-02-12 12:54:10 UTC; 37s ago
 Main PID: 18324 (ntpd)
   CGroup: /system.slice/ntpd.service
           └─18324 /usr/sbin/ntpd -u ntp:ntp -g

Feb 12 12:54:10 ip-172-32-1-137 ntpd[18324]: Listen and drop on 0 v4wildcard 0.0.0.0 UDP 123
Feb 12 12:54:10 ip-172-32-1-137 ntpd[18324]: Listen and drop on 1 v6wildcard :: UDP 123
Feb 12 12:54:10 ip-172-32-1-137 ntpd[18324]: Listen normally on 2 lo 127.0.0.1 UDP 123
Feb 12 12:54:10 ip-172-32-1-137 ntpd[18324]: Listen normally on 3 eth0 172.32.1.137 UDP 123
Feb 12 12:54:10 ip-172-32-1-137 ntpd[18324]: Listen normally on 4 lo ::1 UDP 123
Feb 12 12:54:10 ip-172-32-1-137 ntpd[18324]: Listen normally on 5 eth0 fe80::cb:f7ff:fe78:e4fa UDP 123
Feb 12 12:54:10 ip-172-32-1-137 ntpd[18324]: Listening on routing socket on fd #22 for interface updates
Feb 12 12:54:10 ip-172-32-1-137 ntpd[18324]: 0.0.0.0 c016 06 restart
Feb 12 12:54:10 ip-172-32-1-137 ntpd[18324]: 0.0.0.0 c012 02 freq_set kernel 5.623 PPM
Feb 12 12:54:17 ip-172-32-1-137 ntpd[18324]: 0.0.0.0 c615 05 clock_sync

172.32.1.224 | CHANGED | rc=0 >>
● ntpd.service - Network Time Service
   Loaded: loaded (/usr/lib/systemd/system/ntpd.service; enabled; vendor preset: disabled)
   Active: active (running) since Tue 2019-02-12 12:54:10 UTC; 37s ago
 Main PID: 4598 (ntpd)
   CGroup: /system.slice/ntpd.service
           └─4598 /usr/sbin/ntpd -u ntp:ntp -g

Feb 12 12:54:10 ip-172-32-1-224 ntpd[4598]: Listen and drop on 0 v4wildcard 0.0.0.0 UDP 123
Feb 12 12:54:10 ip-172-32-1-224 ntpd[4598]: Listen and drop on 1 v6wildcard :: UDP 123
Feb 12 12:54:10 ip-172-32-1-224 ntpd[4598]: Listen normally on 2 lo 127.0.0.1 UDP 123
Feb 12 12:54:10 ip-172-32-1-224 ntpd[4598]: Listen normally on 3 eth0 172.32.1.224 UDP 123
Feb 12 12:54:10 ip-172-32-1-224 ntpd[4598]: Listen normally on 4 lo ::1 UDP 123
Feb 12 12:54:10 ip-172-32-1-224 ntpd[4598]: Listen normally on 5 eth0 fe80::66:f7ff:fe05:cb54 UDP 123
Feb 12 12:54:10 ip-172-32-1-224 ntpd[4598]: Listening on routing socket on fd #22 for interface updates
Feb 12 12:54:10 ip-172-32-1-224 ntpd[4598]: 0.0.0.0 c016 06 restart
Feb 12 12:54:10 ip-172-32-1-224 ntpd[4598]: 0.0.0.0 c012 02 freq_set kernel 11.898 PPM
Feb 12 12:54:17 ip-172-32-1-224 ntpd[4598]: 0.0.0.0 c615 05 clock_sync

172.32.1.56 | CHANGED | rc=0 >>
● ntpd.service - Network Time Service
   Loaded: loaded (/usr/lib/systemd/system/ntpd.service; enabled; vendor preset: disabled)
   Active: active (running) since Tue 2019-02-12 12:54:10 UTC; 37s ago
 Main PID: 31926 (ntpd)
   CGroup: /system.slice/ntpd.service
           └─31926 /usr/sbin/ntpd -u ntp:ntp -g

Feb 12 12:54:10 ip-172-32-1-56 ntpd[31926]: Listen and drop on 0 v4wildcard 0.0.0.0 UDP 123
Feb 12 12:54:10 ip-172-32-1-56 ntpd[31926]: Listen and drop on 1 v6wildcard :: UDP 123
Feb 12 12:54:10 ip-172-32-1-56 ntpd[31926]: Listen normally on 2 lo 127.0.0.1 UDP 123
Feb 12 12:54:10 ip-172-32-1-56 ntpd[31926]: Listen normally on 3 eth0 172.32.1.56 UDP 123
Feb 12 12:54:10 ip-172-32-1-56 ntpd[31926]: Listen normally on 4 lo ::1 UDP 123
Feb 12 12:54:10 ip-172-32-1-56 ntpd[31926]: Listen normally on 5 eth0 fe80::f1:a2ff:fe27:247c UDP 123
Feb 12 12:54:10 ip-172-32-1-56 ntpd[31926]: Listening on routing socket on fd #22 for interface updates
Feb 12 12:54:10 ip-172-32-1-56 ntpd[31926]: 0.0.0.0 c016 06 restart
Feb 12 12:54:10 ip-172-32-1-56 ntpd[31926]: 0.0.0.0 c012 02 freq_set kernel 6.349 PPM
Feb 12 12:54:17 ip-172-32-1-56 ntpd[31926]: 0.0.0.0 c615 05 clock_sync

172.32.1.206 | CHANGED | rc=0 >>
● ntpd.service - Network Time Service
   Loaded: loaded (/usr/lib/systemd/system/ntpd.service; enabled; vendor preset: disabled)
   Active: active (running) since Tue 2019-02-12 12:54:10 UTC; 37s ago
 Main PID: 456 (ntpd)
   CGroup: /system.slice/ntpd.service
           └─456 /usr/sbin/ntpd -u ntp:ntp -g

Feb 12 12:54:10 ip-172-32-1-206 ntpd[456]: Listen and drop on 0 v4wildcard 0.0.0.0 UDP 123
Feb 12 12:54:10 ip-172-32-1-206 ntpd[456]: Listen and drop on 1 v6wildcard :: UDP 123
Feb 12 12:54:10 ip-172-32-1-206 ntpd[456]: Listen normally on 2 lo 127.0.0.1 UDP 123
Feb 12 12:54:10 ip-172-32-1-206 ntpd[456]: Listen normally on 3 eth0 172.32.1.206 UDP 123
Feb 12 12:54:10 ip-172-32-1-206 ntpd[456]: Listen normally on 4 lo ::1 UDP 123
Feb 12 12:54:10 ip-172-32-1-206 ntpd[456]: Listen normally on 5 eth0 fe80::64:21ff:fe95:5ea UDP 123
Feb 12 12:54:10 ip-172-32-1-206 ntpd[456]: Listening on routing socket on fd #22 for interface updates
Feb 12 12:54:10 ip-172-32-1-206 ntpd[456]: 0.0.0.0 c016 06 restart
Feb 12 12:54:10 ip-172-32-1-206 ntpd[456]: 0.0.0.0 c012 02 freq_set kernel 12.034 PPM
Feb 12 12:54:17 ip-172-32-1-206 ntpd[456]: 0.0.0.0 c615 05 clock_sync
```
