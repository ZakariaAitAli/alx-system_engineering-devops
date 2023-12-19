# 0x02. Shell, I/O Redirections and filters

## Tasks

#### 0. Hello World
File: `0-hello_world`

Write a script that prints “Hello, World”, followed by a new line to the standard output.
```bash
zakaria@ubuntu:/alx-system_engineering-devops$ ./0-hello_world 
Hello, World
zakaria@ubuntu:/alx-system_engineering-devops$ ./0-hello_world | cat -e
Hello, World$
zakaria@ubuntu:/alx-system_engineering-devops$ 
```

#### 1. Confused smiley
File: `1-confused_smiley`

Write a script that displays a confused smiley "(Ôo)'.
```bash
zakaria@ubuntu:/alx-system_engineering-devops$ ./1-confused_smiley 
"(Ôo)'
zakaria@ubuntu:/alx-system_engineering-devops$ 
```

#### 2. Let's display a file
File: `2-hellofile`

Display the content of the /etc/passwd file.
```bash
zakaria@ubuntu:/alx-system_engineering-devops$ ./2-hellofile
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
zakaria@ubuntu:/alx-system_engineering-devops$
```

#### 3. What about 2?
File: `3-twofiles`

Display the content of /etc/passwd and /etc/hosts
```bash
zakaria@ubuntu:/alx-system_engineering-devops$ ./3-twofiles
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
##
# Host Database
#
# localhost is used to configure the loopback interface
# when the system is booting. Do not change this entry.
##
127.0.0.1   localhost
255.255.255.255 broadcasthost
::1 localhost
zakaria@ubuntu:/alx-system_engineering-devops$
```

#### 4. Last lines of a file
File: `4-lastlines`

Display the last 10 lines of /etc/passwd
```bash
zakaria@ubuntu:/alx-system_engineering-devops$ ./4-lastlines
_assetcache:*:235:235:Asset Cache Service:/var/empty:/usr/bin/false
_coremediaiod:*:236:236:Core Media IO Daemon:/var/empty:/usr/bin/false
_launchservicesd:*:239:239:_launchservicesd:/var/empty:/usr/bin/false
_iconservices:*:240:240:IconServices:/var/empty:/usr/bin/false
_distnote:*:241:241:DistNote:/var/empty:/usr/bin/false
_nsurlsessiond:*:242:242:NSURLSession Daemon:/var/db/nsurlsessiond:/usr/bin/false
_nsurlstoraged:*:243:243:NSURLStorage Daemon:/var/empty:/usr/bin/false
_displaypolicyd:*:244:244:Display Policy Daemon:/var/empty:/usr/bin/false
_astris:*:245:245:Astris Services:/var/db/astris:/usr/bin/false
_krbfast:*:246:-2:Kerberos FAST Account:/var/empty:/usr/bin/false
```

#### 5. I'd prefer the first ones actually
File: `5-firstlines`

Display the first 10 lines of /etc/passwd
```bash
zakaria@ubuntu:/alx-system_engineering-devops$ ./5-firstlines
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
$
```

#### 6. Line #2
File: `6-third_line`

```bash
zakaria@ubuntu:/alx-system_engineering-devops$ cat iacta 
Alea iacta est

Alea iacta est ("The die is cast") is a Latin phrase attributed by Suetonius
(as iacta alea est) to Julius Caesar on January 10, 49 BC
as he led his army across the Rubicon river in Northern Italy. With this step,
he entered Italy at the head of his army in defiance of the Senate and began
his long civil war against Pompey and the Optimates. The phrase has been
adopted in Italian (Il dado è tratto), Romanian (Zarurile au fost aruncate),
Spanish (La suerte está echada), French (Les dés sont jetés), Portuguese (A
sorte está lançada), Dutch (De teerling is geworpen),
German (Der Würfel ist gefallen), Hungarian (A kocka el van vetve) and many other languages to
indicate that events have passed a point of no return.

Read more: https://en.wikipedia.org/wiki/Alea_iacta_est
zakaria@ubuntu:/tmp/h$ ./6-third_line 
Alea iacta est ("The die is cast") is a Latin phrase attributed by Suetonius
zakaria@ubuntu:/tmp/h$ 
```

#### 7. It is a good file that cuts iron without making a noise
File: `7-file`

Write a shell script that creates a file named exactly `\*\\'"Best School"\'\\*$\?\*\*\*\*\*:)` containing the text Best School ending by a new line.

```bash
zakaria@ubuntu:/alx-system_engineering-devops$ ls && ./7-file && ls -l && cat -e \\*
0-mac_and_cheese 7-file 7-file~ Makefile
total 20
-rwxrw-r-- 1 zakaria zakaria 79 Jan 20 06:24 0-mac_and_cheese
-rwxrw-r-- 1 zakaria zakaria 90 Jan 20 06:40 7-file
-rwxrw-r-- 1 zakaria zakaria 69 Jan 20 06:37 7-file~
-rw-rw-r-- 1 zakaria zakaria 14 Jan 20 06:38 Makefile
-rw-rw-r-- 1 zakaria zakaria 17 Jan 20 06:40 '\*\\'"Best School"\'\\*$\?\*\*\*\*\*:)''
Best School$
zakaria@ubuntu:/alx-system_engineering-devops$
```

#### 8. Save current state of directory
File: `8-cwd_state`

Write a script that writes into the file ls_cwd_content the result of the command ls -la. If the file ls_cwd_content already exists, it should be overwritten. If the file ls_cwd_content does not exist, create it.

#### 9. Duplicate last line
File: `9-duplicate_last_line`

Write a script that duplicates the last line of the file iacta

- The file iacta will be in the working directory

#### 10. No more javascript
File: `10-no_more_js`

Write a script that deletes all the regular files (not the directories) with a .js extension that are present in the current directory and all its subfolders.

#### 11. Don't just count your directories, make your directories count
File: `11-directories`

Write a script that counts the number of directories and sub-directories in the current directory.

- The current and parent directories should not be taken into account
- Hidden directories should be counted

#### 12. What’s new
File: `12-newest_files`

Create a script that displays the 10 newest files in the current directory.

Requirements:

- One file per line
- Sorted from the newest to the oldest

#### 13. Being unique is better than being perfect
File: `13-unique`

Create a script that takes a list of words as input and prints only words that appear exactly once.

- Input format: One line, one word
- Output format: One line, one word
- Words should be sorted

#### 14. It must be in that file
File: `14-findthatword`

Display the number of lines that contain the pattern “root” in the file `/etc/passwd`

```shell
zakaria@ubuntu:/alx-system_engineering-devops$ ./14-findthatword
root:*:0:0:System Administrator:/var/root:/bin/sh
daemon:*:1:1:System Services:/var/root:/usr/bin/false
_cvmsroot:*:212:212:CVMS Root:/var/empty:/usr/bin/false
zakaria@ubuntu:/alx-system_engineering-devops$
```

#### 15. Count that word
File: `15-countthatword`

Display the number of lines that contain the pattern “bin” in the file `/etc/passwd`

```shell
zakaria@ubuntu:/alx-system_engineering-devops$ ./14-findthatword | cat -e
46$
```

#### 16. What's next?
File: `16-whatsnext`

Display lines containing the pattern “root” and 3 lines after them in the file `/etc/passwd`.

```shell
zakaria@ubuntu:/alx-system_engineering-devops$ ./16-whatsnext
root:*:0:0:System Administrator:/var/root:/bin/sh
daemon:*:1:1:System Services:/var/root:/usr/bin/false
_uucp:*:4:4:Unix to Unix Copy Protocol:/var/spool/uucp:/usr/sbin/uucico
_taskgated:*:13:13:Task Gate Daemon:/var/empty:/usr/bin/false
_networkd:*:24:24:Network Services:/var/networkd:/usr/bin/false
--
_cvmsroot:*:212:212:CVMS Root:/var/empty:/usr/bin/false
_usbmuxd:*:213:213:iPhone OS Device Helper:/var/db/lockdown:/usr/bin/false
_dovecot:*:214:6:Dovecot Administrator:/var/empty:/usr/bin/false
_dpaudio:*:215:215:DP Audio:/var/empty:/usr/bin/false
zakaria@ubuntu:/alx-system_engineering-devops$
```

#### 17. I hate bins
File: `17-hidethisword`

Display all the lines in the file `/etc/passwd` that do not contain the pattern “bin”.

```shell
zakaria@ubuntu:/alx-system_engineering-devops$ ./17-hidethisword
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
```

#### 18. Letters only please
File: `18-letteronly`

Display all lines of the file `/etc/ssh/sshd_config` starting with a letter.

- include capital letters as well

```shell
zakaria@ubuntu:/alx-system_engineering-devops$ ./18-letteronly
SyslogFacility AUTHPRIV
AuthorizedKeysFile  .ssh/authorized_keys
UsePrivilegeSeparation sandbox # Default for new installations.
AcceptEnv LANG LC_*
Subsystem   sftp    /usr/libexec/sftp-server
zakaria@ubuntu:/alx-system_engineering-devops$
```

#### 19. A to Z
File: `19-AZ`

Replace all characters `A` and `c` from input to `Z` and `e` respectively.

```shell
zakaria@ubuntu:/alx-system_engineering-devops$ echo 'Replace all characters `A` and `c` from input to `Z` and `e`.' | ./19-AZ
Replaze all zharacters `Z` and `e` from input to `Z` and `e`.
zakaria@ubuntu:/alx-system_engineering-devops$
```

#### 20. Without C, you would live in hiago
File: `20-hiago`

Create a script that removes all letters `c` and `C` from input.
    
```shell
zakaria@ubuntu:/alx-system_engineering-devops$ echo 'Create a script that removes all letters `c` and `C` from input.' | ./20-hiago
reate a sript that removes all letters ` and ` from input.
zakaria@ubuntu:/alx-system_engineering-devops$
```

#### 21. esreveR
File: `21-reverse`

Write a script that reverse its input.

```shell
zakaria@ubuntu:/alx-system_engineering-devops$ echo 'Reverse me' | ./21-reverse
em esreveR
zakaria@ubuntu:/alx-system_engineering-devops$
```

#### 22. DJ Cut Killer
File: `22-users_and_homes`

Write a script that displays all users and their home directories, sorted by users.

- Based on the the `/etc/passwd` file

```shell
zakaria@ubuntu:/alx-system_engineering-devops$ ./22-users_and_homes | cat -e
_apt:/nonexistent$
avahi:/run/avahi-daemon$
backup:/var/backups$
bin:/bin$
daemon:/usr/sbin$
games:/usr/games$
geoclue:/var/lib/geoclue$
gnats:/var/lib/gnats$
irc:/run/ircd$
list:/var/list$
lp:/var/spool/lpd$
mail:/var/mail$
man:/var/cache/man$
messagebus:/nonexistent$
news:/var/spool/news$
nobody:/nonexistent$
proxy:/bin$
pulse:/run/pulse$
root:/root$
rtkit:/proc$
sync:/bin$
sys:/dev$
syslog:/home/syslog$
systemd-network:/run/systemd$
systemd-resolve:/run/systemd$
systemd-timesync:/run/systemd$
tcpdump:/nonexistent$
usbmux:/var/lib/usbmux$
uucp:/var/spool/uucp$
uuidd:/run/uuidd$
www-data:/var/www$
zakaria:/home/zakaria$
```

#### 23. Empty casks make the most noise
File: `100-empty_casks`

Write a command that finds all empty files and directories in the current directory and all sub-directories.

- Only the names of the files and directories should be displayed (not the entire path)
- Hidden files should be listed 
- One file name per line
- The listing should end with a new line 
- You are not allowed to use `basename`, `grep`, `egrep`, `fgrep` or `rgrep`

```shell
zakaria@ubuntu:/alx-system_engineering-devops$ ./100-empty_casks | cat -e

zakaria@ubuntu:/alx-system_engineering-devops$ touch -t 1111111111 some_empty_file
zakaria@ubuntu:/alx-system_engineering-devops$ ./100-empty_casks | cat -e
some_empty_file$
zakaria@ubuntu:/alx-system_engineering-devops$ mkdir some_empty_directory
zakaria@ubuntu:/alx-system_engineering-devops$ ./100-empty_casks | cat -e
some_empty_file$
some_empty_directory$
zakaria@ubuntu:/alx-system_engineering-devops$
```

#### 24. A gif is worth ten thousand words
File: `101-gifs`

Write a script that lists all the files with a .gif extension in the current directory and all its sub-directories.

- Hidden files should be listed
- Only regular files (not directories) should be listed
- The names of the files should be displayed without their extensions
- The files should be sorted by byte values, but case-insensitive (file aaa should be listed before file bbb, file .b should be listed before file a, and file Rona should be listed after file jay)
- One file name per line
- The listing should end with a new line
- You are not allowed to use `basename`, `grep`, `egrep`, `fgrep` or `rgrep`

```shell
zaraki@ubuntu:/alx-system_engineering-devops$ ls -laR
```  

#### 25. Acrostic
File: `102-acrostic`

An acrostic is a poem (or other form of writing) in which the first letter (or syllable, or word) of each line (or paragraph, or other recurring feature in the text) spells out a word, message or the alphabet. The word comes from the French acrostiche from post-classical Latin acrostichis). As a form of constrained writing, an acrostic can be used as a mnemonic device to aid memory retrieval. Read more.

Create a script that decodes acrostics that use the first letter of each line.

- The ‘decoded’ message has to end with a new line
- You are not allowed to use `grep`, `egrep`, `fgrep` or `rgrep`

```shell
zakaria@ubuntu:/alx-system_engineering-devops$ ./102-acrostic < An\ Acrostic 
ELIZABETH
zakaria@ubuntu:/alx-system_engineering-devops$
```

#### 26. The biggest fan
File: `103-the_biggest_fan`

Write a script that parses web servers logs in TSV format as input and displays the 11 hosts or IP addresses which did the most requests.

- Order by number of requests, most active host or IP at the top
- You are not allowed to use `grep`, `egrep`, `fgrep` or `rgrep`

```shell
zakaria@ubuntu:/alx-system_engineering-devops$ wget https://s3.amazonaws.com/alx-intranet.hbtn.io/public/nasa_19950801.tsv
zakaria@ubuntu:/alx-system_engineering-devops$ head nasa_19950801.tsv
host    logname time    method  url     response        bytes
in24.inetnebr.com       -       807249601       GET     /shuttle/missions/sts-68/news/sts-68-mcc-05.txt 200     1839
uplherc.upl.com -       807249607       GET     /       304     0
uplherc.upl.com -       807249608       GET     /images/ksclogo-medium.gif      304     0
uplherc.upl.com -       807249608       GET     /images/MOSAIC-logosmall.gif    304     0
uplherc.upl.com -       807249608       GET     /images/USA-logosmall.gif       304     0
ix-esc-ca2-07.ix.netcom.com     -       807249609       GET     /images/launch-logo.gif 200     1713
uplherc.upl.com -       807249610       GET     /images/WORLD-logosmall.gif     304     0
slppp6.intermind.net    -       807249610       GET     /history/skylab/skylab.html     200     1687
piweba4y.prodigy.com    -       807249610       GET     /images/launchmedium.gif        200     11853
zakaria@ubuntu:/alx-system_engineering-devops$ ./103-the_biggest_fan < nasa_19950801.tsv
www-relay.pa-x.dec.com
piweba3y.prodigy.com
www.thyssen.com
130.110.74.81
ix-min1-02.ix.netcom.com
uplherc.upl.com
reggae.iinet.net.au
seigate.sumiden.co.jp
ircgate1.rcc-irc.si
s150.phxslip4.indirect.com
torben.dou.dk
zakaria@ubuntu:/alx-system_engineering-devops$
```
