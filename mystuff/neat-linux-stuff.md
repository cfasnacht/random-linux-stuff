## Random linux stuff

### Grep

```
Grep or:
grep -e this -e that
```

```
Grep xtract password only with:
echo 'challenge password is: <B> password42 blabla ' | grep -oP 'challenge password is: <B> \K\w*'
```

## openssl

```
read local openssl cert:
openssl x509 -text -noout -in certificat.pem
```

```
read local openssl csr:
openssl req -text -noout -in test.csr
```

```
read remote openssl cert:
openssl s_client -showcerts -connect example.com:443
```

### bash scripting:
```
set -x			# activate debugging from here
set +x			# stop debugging from here
set -e      # Exit immediately if a command exits with a non-zero status.
```

## vim

```
#search replace paths in vim:
:%s#/etc/ssl/certs/#/etc/pki/tls/certs#gc
```

## Asorted
```
join two files:
file1 : a,b
fiel2 : b,c
result: a,b,c
join -t , -1 2 -2 1 -o 1.1,1.2,2.2 <(sort -k 2 -t , file1) <(sort -t , file2)
```

```
replace # commented and empty lines:
sed -e 's/#.*$//' -e '/^$/d'
```

```
make curl to not use a proxy:
curl --noproxy "*" example.com
```

```
Selinux, context recursive persisent:
semanage fcontext -a -t postgresql_db_t "/data01/pgsql(/.*)?"
```

```
find and rename
find /etc/httpd/conf.d -name "*.conf" -exec rename conf conf2 {} \;
```

```
#fireall-cmd log all:
firewall-cmd --set-log-denied=all
```

```
SSH Tunnel:
Tunnel 8080 on the localhost to 192.168.58.20 port 44323
ssh -L 8080:192.168.58.1:44323 root@192.168.58.1
```
