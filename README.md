# Linux
### check connectivity
```
ssh -v -x -o connectitimeout=1 server1 -p 80

# check NAME or ID in /etc/os-release
$ grep "^NAME=" /etc/os-release |cut -d "=" -f 2 | sed -e 's/^"//' -e 's/"$//'   
Ubuntu
$ python -mplatform 
Linux-4.4.0-116-generic-x86_64-with-Ubuntu-16.04-xenial  
$ awk -F= '/^NAME/{print $2}' /etc/os-release
"Ubuntu"

```
