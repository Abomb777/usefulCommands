# usefulCommands
Useful commands linux
```sh
find . -type f -size +500000k -exec ls -lh {} \; | awk '{ print $9 ": " $5 }'
```
find / -name id_rsa
ssh-keygen -t rsa
cat /root/.ssh/id_rsa.pub >> /root/.ssh/authorized_keys
ls -la  /root/.ssh/authorized_keys
chmod 644 /root/.ssh/authorized_keys
vim /root/.ssh/id_rsa
