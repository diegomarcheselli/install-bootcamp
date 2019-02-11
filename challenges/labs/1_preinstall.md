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


# Swappines
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


