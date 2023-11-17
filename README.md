# Linux
- [Free AWS VPN server](https://medium.com/analytics-vidhya/setup-a-free-vpn-service-on-aws-613fcec6e7c6)
- [Git Markdown](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#links)
- [linux command cursor move](https://github.com/fliptheweb/bash-shortcuts-cheat-sheet)
- [vi cheat sheet](https://www.cse.scu.edu/~yfang/coen11/vi-CheatSheet.pdf)

### Regex Test
- [regexr.com](https://regexr.com)
- [regex101.com](https://regex101.com)

### Curl get certificate
curl -kv -w '\n%{certs}\n' https://blah.com

### check disk space
```
du -csh *
```

### Add user
```
ssh-keygen -t ed25519 -C "myemail@blah.com"

useradd -m lisa  #/home/lisa
passwd lisa
usermod -aG sudo lisa

groupadd sudo

useradd -m -p $(perl -e 'print crypt($ARGV[0], "password")' 'mypass') user1

ssh-keygen -t rsa -b 4096
ssh-keygen -t dsa 
ssh-keygen -t ecdsa -b 521
ssh-keygen -t ed25519

/var/log/secure 

```
### Timezone -> EST
```
timedatectl list-timezones |  egrep  -o "America/N.*"
timedatectl set-timezone "America/New_York"
timedatectl status

timedatectl set-ntp true
```
###
https://rentes.github.io/unix/utilities/2015/07/27/moreutils-package/

###
- https://www.base64decode.org/
- https://www.sslchecker.com/certdecoder
- https://jwt.io/


### Self signed certificate: key, crt

```
openssl req -x509 -newkey rsa:4096 -sha256 -days 3650 -nodes \
  -keyout example.key -out example.crt -subj "/CN=example.com" \
  -addext "subjectAltName=DNS:example.com,DNS:www.example.net"
```

# how to find email address github user
https://api.github.com/users/jhong40/events/public

###
Shell Scripting: Expert Recipes for Linux, Bash, and More
https://doc.lagout.org/operating%20system%20/linux/Commands%20and%20Shell%20Programming/Shell%20Scripting.pdf
###
https://publib.boulder.ibm.com/httpserv/cookbook/Troubleshooting-Troubleshooting_Operating_Systems-Troubleshooting_Linux.html

### Time stamp
https://stackoverflow.com/questions/17066250/create-timestamp-variable-in-bash-script
https://www.geeksforgeeks.org/date-command-linux-examples/

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
Ctrl+C – Kill current process
Ctrl+D – Close Terminal
Ctrl+Z – Suspend. Use “fg process” to return
Ctrl+S – Suspend output to screen
Ctrl+Q – Resume output to screen
Tab – Completion for file/folder names

Command History
Ctrl+P or Up Arrow - Previous Command
Ctrl+N or Down Arrow - Next Command
Ctrl+R - Recall command matching search
  Ctrl+O - Run the command you found with Ctrl+R
  Ctrl+T - leave the command without run
  Ctrl+G - Leave history searching mode without running a command
!! - Repeat previous command
!:n – Repeat specific argument from previous command
!:n:m – Repeat range of arguments from previous command
!:n:$ - Repeat range of arguments from n to end from previous command
!* - Repeat All arguments from previous command
Alt + . - Show Last argument from previous command
^abc­^­def -  Run previous command, replacing abc with def

Move Cursor
Ctrl+A or Home – Beginning of the Line
Ctrl+E or End – End of the Line
Ctrl+B or Left Arrow – Back one Character
Ctrl+F or Right Arrow – Forward one Character
Ctrl+Left Arrow or Alt+B – Back one Word
Ctrl+Right Arrow or Alt+F – Forward one Word
Ctrl+XX – Toggle between Beginning and End of Line
Ctrl+M - Enter

Deleting Text
Ctrl+L – Clear Screen
Ctrl+D or Delete – Delete character under the cursor
Ctrl+H or Backspace – Delete character before the cursor
Alt+D – Delete the Word after the cursor

Fix Typos
Alt+T or Esc+T - Swap current word with previous word
Ctrl+T Swap the last two characters before the cursor with each other
Ctrl+_ (Ctrl+Shift+-)  - Undo your last key press
Ctrl+U – Clear all text from Cursor to Beginning of Line
Alt+R – Revert line

Capitalisation
Alt+C – Capitalise current Character
Alt+U – Capitalise current Word  from cursor
Alt+L – Lowercase current Word from cursor

Cut and Paste from Bash Clipboard
Ctrl+W - Cut the Word before the cursor
Ctrl+K - all text from Cursor to End of Line
Ctrl+U - Cut all text from Cursor to Beginning of Line
Ctrl+Y – Paste

Cut and Paste from System Clipboard
Ctrl+Alt+C – Copy highlighted text
Ctrl+Alt+V or Middle Click – Paste
```
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

7,9co.  # copy line 7,8,9 to current loc
H, M, L # top, middle, bottom


5>>     # indent 5 lines from the currosr
5<<     # remove indent for 5 lines
.       # repeat the previouse action

truncate -s 0 myapp.log   # resize the log to 0 at run time
mount | column -t
```

```
######################### vi usage
            
 gg - beging of F
 G - end of F
 H - beging of screen
 L - end of screen
 M - middle of screen
 w - => word
 b - <= word
 
 i - insert br
 a - insert after
 o - insert one line below
 s - replace/insert           
 c - followed by w,$ remove those and insert         
 
 I - insert at the begining of l
 A - insert at the end of l
 O - insert one line above
 S - replace the whole line and insert
 C - delete the rest of line and insert
           
 v (lower v) - visual mode, 
 shift+v (cap V) - visual mode select line
 ctrol+v  - visual mode select block
 move arrow to select
 > 
 <
 
set expandtab
set tabstop=2
set shiftwidth=2
      
set all    # check all the setting       
set list   # show space, tab, endofline$
set paste  # copy web yaml to vi
set ruler  # see the line,column number
set number  # number each line
set nu   # set nonu, set nu!
set rnu  # set nornu, set rnu!

:help expandtab # help tabstop   
:vsplit    # 
:wincmd w  # move to the next window
 ```
``` 
Ctrl + U = Delete left of the cursor
Ctrl + K = Delete right of the cursor

Ctrl + D = Delete character at the cursor 

Ctrl + W = Delete word on the left
Alt +  D = Delete the word on the right

:sp -> slit windows top/bottom
:vsp -> split -> left/right
ctr-ww -> switch window

shift+v: enter visual mode, hight the line
shift+downarrow: 
shift+up arrow
shift >: move right
shift <: move left
. : repeat the above


```
