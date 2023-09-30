# 0x00. Shell, basics

## Tasks

#### 0. Where am I? 
File: `0-current_working_directory`

Write a script that prints the absolute path name of the current working directory.

Example:
```
$ ./0-current_working_directory
/root/alx-system_engineering-devops/0x00-shell_basics
$
```

#### 1. What’s in there?
File: `1-listit`

Display the contents list of your current directory.

Example:
```
$ ./1-listit
Applications    Documents   Dropbox Movies Pictures
Desktop Downloads   Library Music Public
$
```

#### 2. There is no place like home
File: `2-bring_me_home`

Write a script that changes the working directory to the user’s home directory.

- You are not allowed to use any shell variables
```
zakaria@ubuntu:/tmp$ pwd
/tmp
zakaria@ubuntu:/tmp$ echo $HOME
/home/zakaria
zakaria@ubuntu:/tmp$ source ./2-bring_me_home
zakaria@ubuntu:~$ pwd
/home/zakaria
zakaria@ubuntu:~$ 
```

#### 3. The long format
File: `3-listfiles`

Display current directory contents in a long format

Example:
```
$ ./3-listfiles
total 32
-rwxr-xr-x@ 1 zakaria zakaria 18 Jan 25 00:19 0-current_working_directory
-rwxr-xr-x@ 1 zakaria zakaria 19 Jan 25 00:23 1-listit
-rwxr-xr-x@ 1 zakaria zakaria 18 Jan 25 00:29 2-bring_me_home
-rwxr-xr-x@ 1 zakaria zakaria 18 Jan 25 00:39 3-listfiles
$
```

#### 4. Hidden files
File: `4-listmorefiles`

Display current directory contents, including hidden files. Use the long format.

Example:
```
$ ./4-listmorefiles
total 32
drwxr-xr-x@ 6 zakaria zakaria 204 Jan 25 00:29 .
drwxr-xr-x@ 43 zakaria zakaria 1462 Jan 25 00:19 ..
-rwxr-xr-x@ 1 zakaria zakaria 18 Jan 25 00:19 0-current_working_directory
-rwxr-xr-x@ 1 zakaria zakaria 19 Jan 25 00:23 1-listit
-rwxr-xr-x@ 1 zakaria zakaria 18 Jan 25 00:29 2-bring_me_home
-rwxr-xr-x@ 1 zakaria zakaria 18 Jan 25 00:39 3-listfiles
-rwxr-xr-x@ 1 zakaria zakaria 18 Jan 25 00:41 4-listmorefiles
$
```

#### 5. I love numbers
File: `5-listfilesdigitonly`

Display current directory contents.
- Long format
- with user and group IDs displayed numerically
- And hidden files

Example:
```
$ ./5-listfilesdigitonly
total 32
drwxr-xr-x@ 6 501 20 204 Jan 25 00:29 .
drwxr-xr-x@ 43 501 20 1462 Jan 25 00:19 ..
-rwxr-xr-x@ 1 501 20 18 Jan 25 00:19 0-current_working_directory
-rwxr-xr-x@ 1 501 20 18 Jan 25 00:23 1-listfiles
-rwxr-xr-x@ 1 501 20 19 Jan 25 00:29 2-bring_me_home
-rwxr-xr-x@ 1 501 20 20 Jan 25 00:39 3-listfiles
-rwxr-xr-x@ 1 501 20 18 Jan 25 00:41 4-listmorefiles
-rwxr-xr-x@ 1 501 20 18 Jan 25 00:43 5-listfilesdigitonly
$
```

#### 6. Welcome
File: `6-firstdirectory`
Create a script that creates a directory named my_first_directory in the /tmp/ directory.

Example:
```
$ ./6-firstdirectory
$ file /tmp/my_first_directory/
/tmp/my_first_directory/: directory
$
```

#### 7. Betty in my first directory
File: `7-movethatfile`
Move the file betty from /tmp/ to /tmp/my_first_directory.

Example:
```
$ ./7-movethatfile
$ ls /tmp/my_first_directory/
betty
$
```

#### 8. Bye bye Betty
File: `8-firstdelete`

Delete the file betty.

- The file betty is in /tmp/my_first_directory

Example:
```
$ ./8-firstdelete
$ ls /tmp/my_first_directory/
$
```

#### 9. Bye bye My first directory
File: `9-firstdirdeletion`

Delete the directory my_first_directory that is in the /tmp directory.

Example:
```
$ ./9-firstdirdeletion
$ file /tmp/my_first_directory
/tmp/my_first_directory: cannot open `/tmp/my_first_directory' (No such file or directory)
$
```

#### 10. Back to the future
File: `10-back`

Write a script that changes the working directory to the previous one.

Example:
```
zakaria@ubuntu:/tmp$ pwd
/tmp
zakaria@ubuntu:/tmp$ cd /var
zakaria@ubuntu:/var$ pwd
/var
zakaria@ubuntu:/var$ source ./10-back
/tmp
zakaria@ubuntu:/tmp$ pwd
/tmp
```

#### 11. Lists
File: `11-lists`

Write a script that lists all files (even hidden ones) in the current directory and the parent of the working directory and the /boot directory (in this order), in long format.

#### 12. File type
File: `12-file_type`

Write a script that prints the type of the file named iamafile. The file iamafile will be in the /tmp directory when we will run your script.

Example:
```
$ ./12-file_type
/tmp/iamafile: ELF 64-bit LSB  executable, x86-64, version 1 (SYSV), dynamically linked (uses shared libs), for GNU/Linux 2.6.24, BuildID[sha1]=bd39c07194a778ccc066fc963ca152bdfaa3f971, stripped
```

#### 13. We are symbols, and inhabit symbols
File: `13-symbolic_link`

Create a symbolic link to /bin/ls, named __ls__. The symbolic link should be created in the current working directory.

```
zakaria@ubuntu:/tmp/sym$$ ls -la
total 144
drwxrwxr-x  2 ubuntu ubuntu   4096 Sep 20 03:24 .
drwxrwxrwt 12 root   root   139264 Sep 20 03:24 ..
zakaria@ubuntu:/tmp/sym$$./13-symbolic_link
zakaria@ubuntu:/tmp/sym$$ ls -la
total 144
drwxrwxr-x  2 ubuntu ubuntu   4096 Sep 20 03:24 .
drwxrwxrwt 12 root   root   139264 Sep 20 03:24 ..
lrwxrwxrwx  1 ubuntu ubuntu      7 Sep 20 03:24 __ls__ -> /bin/ls
```

#### 14. Copy HTML files
File: `14-copy_html`

Create a script that copies all the HTML files from the current working directory to the parent of the working directory, but only copy files that did not exist in the parent of the working directory or were newer than the versions in the parent of the working directory.

You can consider that all HTML files have the extension .html

#### 15. Let’s move
File: `100-lets_move`

Create a script that moves all files beginning with an uppercase letter to the directory /tmp/u.

You can assume that the directory /tmp/u will exist when we will run your script
```
zakaria@ubuntu:/tmp/sym$ ls -la
total 148
drwxrwxr-x  3 ubuntu ubuntu   4096 Sep 20 03:33 .
drwxrwxrwt 12 root   root   139264 Sep 20 03:26 ..
-rw-rw-r--  1 ubuntu ubuntu      0 Sep 20 03:32 My_file
lrwxrwxrwx  1 ubuntu ubuntu      7 Sep 20 03:24 __ls__ -> /bin/ls
-rw-rw-r--  1 ubuntu ubuntu      0 Sep 20 03:32 Elif_ym
-rw-rw-r--  1 ubuntu ubuntu      0 Sep 20 03:32 random_file
zakaria@ubuntu:/tmp/sym$ ls -la /tmp/u
total 8
drwxrwxr-x 2 ubuntu ubuntu 4096 Sep 20 03:33 .
drwxrwxr-x 3 ubuntu ubuntu 4096 Sep 20 03:33 ..
ubuntu@ip-172-31-63-244:/tmp/sym$ ./100-lets_move
ubuntu@ip-172-31-63-244:/tmp/sym$ ls -la
total 148
drwxrwxr-x  3 ubuntu ubuntu   4096 Sep 20 03:33 .
drwxrwxrwt 12 root   root   139264 Sep 20 03:26 ..
lrwxrwxrwx  1 ubuntu ubuntu      7 Sep 20 03:24 __ls__ -> /bin/ls
-rw-rw-r--  1 ubuntu ubuntu      0 Sep 20 03:32 random_file
zakaria@ubuntu:/tmp/sym$ ls -la /tmp/u
total 8
drwxrwxr-x 2 ubuntu ubuntu 4096 Sep 20 03:33 .
drwxrwxr-x 3 ubuntu ubuntu 4096 Sep 20 03:33 ..
-rw-rw-r-- 1 ubuntu ubuntu    0 Sep 20 03:32 My_file
-rw-rw-r-- 1 ubuntu ubuntu    0 Sep 20 03:32 Elif_ym
```

#### 16. Clean Emacs
File: `101-clean_emacs`

Create a script that deletes all files in the current working directory that end with the character ~.
```
zakaria@ubuntu:/tmp/sym$ ls
main.c  main.c~  Makefile~
zakaria@ubuntu:/tmp/sym$ ./101-clean_emacs
zakaria@ubuntu:/tmp/emacs$ ls
main.c
zakaria@ubuntu:/tmp/emacs$
```

#### 17. Tree
File: `102-tree`

Create a script that creates the directories welcome/, welcome/to/ and welcome/to/school in the current directory.

You are only allowed to use two spaces (and lines) in your script, not more.
```
zakaria@ubuntu:/tmp/h$ ls -l
total 4
-rwxrw-r-- 1 julien julien 44 Sep 20 12:09 102-tree
zakaria@ubuntu:/tmp/h$ wc -l 102-tree 
2 102-tree
zakaria@ubuntu:/tmp/h$ head -1 102-tree 
#!/bin/bash
zakaria@ubuntu:/tmp/h$ tr -cd ' ' < 102-tree | wc -c # you do not have to understand this yet, but the result should be 2, 1 or 0
2
zakaria@ubuntu:/tmp/h$ ./102-tree 
zakaria@ubuntu:/tmp/h$ ls
102-tree  welcome
zakaria@ubuntu:/tmp/h$ ls welcome/
to
zakaria@ubuntu:/tmp/h$ ls -l welcome/to
total 4
drwxrwxr-x 2 julien julien 4096 Sep 20 12:11 school
zakaria@ubuntu:/tmp/h$ 
```

#### 18. Life is a series of commas, not periods
File: `103-commas`

Write a command that lists all the files and directories of the current directory, separated by commas (,).

- Directory names should end with a slash (/)
- Files and directories starting with a dot (.) should be listed
- The listing should be alpha ordered, except for the directories . and .. which should be listed at the very beginning
- Only digits and letters are used to sort; Digits should come first
- You can assume that all the files we will test with will have at least one letter or one digit
- The listing should end with a new line

```
zakaria@ubuntu:~/$ ls -a
.  ..  0-commas  0-commas-checks  1-empty_casks  2-gifs  3-directories 4-zeros
5-rot13 6-odd  7-sort_rot13  Makefile  quote  .test  test_dir  test.var
zakaria@ubuntu:~/$ ./103-commas
./, ../, 0-commas, 0-commas-checks/, 1-empty_casks, 2-gifs, 3-directories, 4-zeros,
5-rot13, 6-odd, 7-sort_rot13, Makefile, quote, .test, test_dir/, test.var
zakaria@ubuntu:~/$
```
#### 19. File type: School
File: `school.mgc`

Create a magic file school.mgc that can be used with the command file to detect School data files. School data files always contain the string SCHOOL at offset 0.
```
zakaria@ubuntu:/tmp/magic$ cp /bin/ls .
zakaria@ubuntu:/tmp/magic$ ls -la
total 268
drwxrwxr-x  2 ubuntu ubuntu   4096 Sep 20 02:44 .
drwxrwxrwt 11 root   root   139264 Sep 20 02:44 ..
-rw-r--r--  1 ubuntu ubuntu    496 Sep 20 02:42 school.mgc
-rwxr-xr-x  1 ubuntu ubuntu 110080 Sep 20 02:43 ls
-rw-rw-r--  1 ubuntu ubuntu     50 Sep 20 02:06 thisisaschoolfile
-rw-rw-r--  1 ubuntu ubuntu     30 Sep 20 02:16 thisisatextfile
zakaria@ubuntu:/tmp/magic$ file --mime-type -m school.mgc *
school.mgc:         application/octet-stream
ls:                    application/octet-stream
thisisaschoolfile: School
thisisatextfile:       text/plain
zakaria@ubuntu:/tmp/magic$ file -m school.mgc *
school.mgc:         data
ls:                    data
thisisaschoolfile: School data
thisisatextfile:       ASCII text
zakaria@ubuntu:/tmp/magic$
```
