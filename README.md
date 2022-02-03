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

#### trick
https://www.youtube.com/watch?v=qS0phIqRy8Y
```
ctr+l   # clear screen

ctr+z   # put the current proc into bg
jobs    # check bg process
fg      # bring it back to fg

!!      # run last command
sudo !! # run sudo {last command}
!5      # run num 5 command

ctr+r   # search command

HISTTIMEFORMAT="%Y-%m-%d %T "   # add $/.bashrc
ctr+u   # delete the current command
ctr+a   # goto begining of the command
ctr+e   # goto the end of the command

truncate -s 0 myapp.log   # resize the log to 0 at run time
mount | column -t



```
