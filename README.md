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
## vi usage
            
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
