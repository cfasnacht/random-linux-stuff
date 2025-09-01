## Random linux stuff

## Grep

```
Grep or:
grep -e this -e that
```

```
highlight with grep: (show interfaces with link:)
ip a | grep --color=auto -C 10 ' UP'
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

## bash scripting:

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

```
Personal cheat sheet:
f : => jumps first : on the same line
```

## tmux

```
# tmux print tmux session output without attaching:
tmux capture-pane -pt "$target-pane" -E -10
# [-E end-line] [-S start-line] [-t target-pane]
```

## Asorted

```
show filename and content of multiple files:
head -n 9999 *.txt
```


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


```
print current network load:
nload <interface name>
```

```
print UDP network statistics: (e.g. if there are UDP connection problems)
netstat -suna
```

```
Git:
find last modified branch
git for-each-ref --sort=-committerdate refs/heads/
```

```
Docker / podman:
docker/podman run -ti --entrypoint=/bin/sh  -p 127.0.0.1:5000:5000 --mount type=bind,source="$(pwd)"/client_secrets.json,target=/web/pitc-forms/client_secrets.json --env-file=.env registry.puzzle.ch/puzzle/forms:git-cf36980b
```

```
openshift debug:
oc debug forms-273-6vngb --as-root
oc port-forward forms-273-6vngb-debug 5000

Im terminal env -0 verwenden um die env variables anzuschauen. echo hat bei mir nicht funktioniert, hat ein newline nicht ausgegeben
```
