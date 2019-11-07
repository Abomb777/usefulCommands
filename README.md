# usefulCommands
Useful commands linux
```sh
find . -type f -size +500000k -exec ls -lh {} \; | awk '{ print $9 ": " $5 }'
```
