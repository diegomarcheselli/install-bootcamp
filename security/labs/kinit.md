## test user kinit


```
[ec2-user@ip-172-32-1-224 ~]$ ^C
[ec2-user@ip-172-32-1-224 ~]$ kinit diegomarcheselli
Password for diegomarcheselli@ARDA.COM:
[ec2-user@ip-172-32-1-224 ~]$ klist
Ticket cache: FILE:/tmp/krb5cc_1000
Default principal: diegomarcheselli@ARDA.COM

Valid starting       Expires              Service principal
02/14/2019 12:23:44  02/15/2019 12:23:44  krbtgt/ARDA.COM@ARDA.COM
        renew until 02/21/2019 12:23:44
[ec2-user@ip-172-32-1-224 ~]$

```
