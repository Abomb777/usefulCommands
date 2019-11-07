# usefulCommands
Useful commands linux
```sh
find . -type f -size +500000k -exec ls -lh {} \; | awk '{ print $9 ": " $5 }'
```
```sh
find / -name id_rsa
ssh-keygen -t rsa
cat /root/.ssh/id_rsa.pub >> /root/.ssh/authorized_keys
ls -la  /root/.ssh/authorized_keys
chmod 644 /root/.ssh/authorized_keys
vim /root/.ssh/id_rsa
```

```sh
netstat -a
netstat -ant | grep 800 | grep EST | wc -l
netstat -ant | grep 80 | grep EST | wc -l
netstat -ant | grep 443 | grep EST | wc -l
netstat -ant | grep  | grep EST | wc -l
netstat -ant  | grep EST | wc -l
netstat -ant | grep 80 | grep EST | wc -l
netstat -ant | grep 80 | wc -l
tcpdump -s 0 -X 'tcp dst port 80'
service httpd restart
tcpdump -s 0 -X 'tcp dst port 80'
tcpdump
tcpdump -s 0 -X 'tcp dst port 80'
ngrep -q '^GET .* HTTP/1.[01]'
yum install ngrep
ngrep -q '^GET .* HTTP/1.[01]'
ngrep -q '^GET .* HTTP/1.'
ngrep -q '^GET .* HTTP'
ngrep
ngrep -l -q -d eth0 -i "^GET |^POST " tcp and port 80
find / -type f -size +500000k -exec ls -lh {} \; | awk '{ print $9 ": " $5 }'
```
grep -rnw '/var/www/html/' -e 'quickview'
