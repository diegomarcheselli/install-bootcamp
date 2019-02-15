 sudo cat /var/kerberos/krb5kdc/kdc.conf

[kdcdefaults]
 kdc_ports = 88
 kdc_tcp_ports = 88

[realms]
 DIEGO.ABC
  #master_key_type = aes256-cts
  acl_file = /var/kerberos/krb5kdc/kadm5.acl
  dict_file = /usr/share/dict/words
  admin_keytab = /var/kerberos/krb5kdc/kadm5.keytab
  supported_enctypes = aes256-cts:normal aes128-cts:normal des3-hmac-sha1:normal arcfour-hmac:normal camellia256-cts:normal camellia128-cts:normal des-hmac-sha1:normal des-cbc-md5:normal des-cbc-crc:normal

  max_life = 1d
  max_renewable_life = 7d
 }



[ec2-user@ip-172-32-1-249 ~]$ cat  /etc/krb5.conf
# Configuration snippets may be placed in this directory as well
includedir /etc/krb5.conf.d/

[logging]
 default = FILE:/var/log/krb5libs.log
 kdc = FILE:/var/log/krb5kdc.log
 admin_server = FILE:/var/log/kadmind.log

[libdefaults]
 dns_lookup_realm = false
 ticket_lifetime = 24h
 renew_lifetime = 7d
 forwardable = true
 rdns = false
# pkinit_anchors = /etc/pki/tls/certs/ca-bundle.crt
 default_realm = DIEGO.ABC
# default_ccache_name = KEYRING:persistent:%{uid}

 default_tgs_enctypes = aes256-cts
 default_tkt_enctypes = aes256-cts

[realms]
 DIEGO.ABC = {
  kdc = ip-172-32-1-28
  admin_server = ip-172-32-1-28
 }

[domain_realm]
 .ip-172-32-1-28 = DIEGO.ABC
 ip-172-32-1-28.com = DIEGO.ABC
