# 0x02. Shell, I/O Redirections and filters

## Tasks

#### 0. Hello World
File: `0-hello_world`

Write a script that prints “Hello, World”, followed by a new line to the standard output.
```
zakaria@ubuntu:/tmp/h$ ./0-hello_world 
Hello, World
zakaria@ubuntu:/tmp/h$ ./0-hello_world | cat -e
Hello, World$
zakaria@ubuntu:/tmp/h$ 
```

#### 1. Confused smiley
File: `1-confused_smiley`

Write a script that displays a confused smiley "(Ôo)'.
```
zakaria@ubuntu:/tmp/h$ ./1-confused_smiley 
"(Ôo)'
zakaria@ubuntu:/tmp/h$ 
```

#### 2. Let's display a file
File: `2-hellofile`

Display the content of the /etc/passwd file.
```
$ ./2-hellofile
##
# User Database
#
# Note that this file is consulted directly only when the system is running
# in single-user mode. At other times this information is provided by
# Open Directory.
#
# See the opendirectoryd(8) man page for additional information about
# Open Directory.
##
nobody:*:-2:-2:Unprivileged User:/var/empty:/usr/bin/false
root:*:0:0:System Administrator:/var/root:/bin/sh
daemon:*:1:1:System Services:/var/root:/usr/bin/false
_uucp:*:4:4:Unix to Unix Copy Protocol:/var/spool/uucp:/usr/sbin/uucico
_taskgated:*:13:13:Task Gate Daemon:/var/empty:/usr/bin/false
_networkd:*:24:24:Network Services:/var/networkd:/usr/bin/false
_installassistant:*:25:25:Install Assistant:/var/empty:/usr/bin/false
_lp:*:26:26:Printing Services:/var/spool/cups:/usr/bin/false
_postfix:*:27:27:Postfix Mail Server:/var/spool/postfix:/usr/bin/false
_scsd:*:31:31:Service Configuration Service:/var/empty:/usr/bin/false
_ces:*:32:32:Certificate Enrollment Service:/var/empty:/usr/bin/false
_mcxalr:*:54:54:MCX AppLaunch:/var/empty:/usr/bin/false
_krbfast:*:246:-2:Kerberos FAST Account:/var/empty:/usr/bin/false
$
```


