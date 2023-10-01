# 0x01. Shell, permissions

## Tasks

#### 0. My name is Betty
File: `0-iam_betty`

Create a script that switches the current user to the user betty.
```
zakaria@ubuntu:/tmp/h$ tail -1 0-iam_betty | wc -c
9
zakaria@ubuntu:/tmp/h$
```

#### 1. Who am I
File: `1-who_am_i`

Write a script that prints the effective username of the current user.
```
zakaria@ubuntu:/tmp/h$ ./1-who_am_i
zakaria
zakaria@ubuntu:/tmp/h$ 
```

#### 2. Groups
File: `2-groups`

Write a script that prints all the groups the current user is part of.
```
zakaria@ubuntu:/tmp/h$ ./2-groups
zakaria adm cdrom sudo dip plugdev lpadmin sambashare
zakaria@ubuntu:/tmp/h$ 
```

#### 3. New owner
File: `3-new_owner`

Write a script that changes the owner of the file hello to the user betty.
```
zakaria@ubuntu:/tmp/h$ ls -l
total 4
-rwxrw-r-- 1 zakaria zakaria 30 Sep 20 14:23 3-new_owner
-rw-rw-r-- 1 zakaria zakaria  0 Sep 20 14:18 hello
zakaria@ubuntu:/tmp/h$ sudo ./3-new_owner 
zakaria@ubuntu:/tmp/h$ ls -l
total 4
-rwxrw-r-- 1 zakaria zakaria 30 Sep 20 14:23 3-new_owner
-rw-rw-r-- 1 betty  zakaria  0 Sep 20 14:18 hello
zakaria@ubuntu:/tmp/h$
```

#### 4. Empty!
File: `4-empty`

Write a script that creates an empty file called hello.

#### 5. Execute
File: `5-execute`

Write a script that adds execute permission to the owner of the file hello.
```
zakaria@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 zakaria zakaria 28 Sep 20 14:26 5-execute
-rw-rw-r-- 1 zakaria zakaria 23 Sep 20 14:25 hello
zakaria@ubuntu:/tmp/h$ ./hello
bash: ./hello: Permission denied
zakaria@ubuntu:/tmp/h$ ./5-execute 
zakaria@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 zakaria zakaria 28 Sep 20 14:26 5-execute
-rwxrw-r-- 1 zakaria zakaria 23 Sep 20 14:25 hello
zakaria@ubuntu:/tmp/h$ 
```

#### 6. Multiple permissions
File: `6-multiple_permissions`

Write a script that adds execute permission to the owner and the group owner, and read permission to other users, to the file hello.
```
zakaria@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 zakaria zakaria 36 Sep 20 14:31 6-multiple_permissions
-r--r----- 1 zakaria zakaria 23 Sep 20 14:25 hello
zakaria@ubuntu:/tmp/h$ ./6-multiple_permissions 
zakaria@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 zakaria zakaria 36 Sep 20 14:31 6-multiple_permissions
-r-xr-xr-- 1 zakaria zakaria 23 Sep 20 14:25 hello
zakaria@ubuntu:/tmp/h$ 
```

#### 7. Everybody!
File: `7-everybody`

Write a script that adds execution permission to the owner, the group owner and the other users, to the file hello
```
zakaria@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 zakaria zakaria 28 Sep 20 14:35 7-everybody
-rw-r----- 1 zakaria zakaria 23 Sep 20 14:25 hello
zakaria@ubuntu:/tmp/h$ ./7-everybody 
zakaria@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 zakaria zakaria 28 Sep 20 14:35 7-everybody
-rwxr-x--x 1 zakaria zakaria 23 Sep 20 14:25 hello
zakaria@ubuntu:/tmp/h$ 
```

#### 8. James Bond
File: `8-James_Bond`

Write a script that sets the permission to the file hello as follows:

- Owner: no permission at all
- Group: no permission at all
- Other users: all the permissions
```
zakaria@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 zakaria zakaria 28 Sep 20 14:40 8-James_Bond
-rwxr-x--x 1 zakaria zakaria 23 Sep 20 14:25 hello
zakaria@ubuntu:/tmp/h$ ./8-James_Bond 
zakaria@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 zakaria zakaria 28 Sep 20 14:40 8-James_Bond
-------rwx 1 zakaria zakaria 23 Sep 20 14:25 hello
zakaria@ubuntu:/tmp/h$ 
```

#### 9. John Doe
File: `9-John_Doe`

Write a script that sets the mode of the file hello to this:
```
-rwxr-x-wx 1 zakaria zakaria 23 Sep 20 14:25 hello
```

#### 10. Look in the mirror
File: `10-mirror_permissions`

Write a script that sets the mode of the file hello the same as olleh’s mode.
```
zakaria@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 zakaria zakaria 42 Sep 20 14:45 10-mirror_permissions
-rwxr-x-wx 1 zakaria zakaria 23 Sep 20 14:25 hello
-rw-rw-r-- 1 zakaria zakaria  0 Sep 20 14:43 olleh
zakaria@ubuntu:/tmp/h$ ./10-mirror_permissions 
zakaria@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 zakaria zakaria 42 Sep 20 14:45 10-mirror_permissions
-rw-rw-r-- 1 zakaria zakaria 23 Sep 20 14:25 hello
-rw-rw-r-- 1 zakaria zakaria  0 Sep 20 14:43 olleh
zakaria@ubuntu:/tmp/h$ 
```

#### 11. Directories
File: `11-directories_permissions`

Create a script that adds execute permission to all subdirectories of the current directory for the owner, the group owner and all other users.

Regular files should not be changed.
```
zakaria@ubuntu:/tmp/h$ ls -l
total 20
-rwxrwxr-x 1 zakaria zakaria   24 Sep 20 14:53 11-directories_permissions
drwx------ 2 zakaria zakaria 4096 Sep 20 14:49 dir0
drwx------ 2 zakaria zakaria 4096 Sep 20 14:49 dir1
drwx------ 2 zakaria zakaria 4096 Sep 20 14:49 dir2
-rw-rw-r-- 1 zakaria zakaria   23 Sep 20 14:25 hello
zakaria@ubuntu:/tmp/h$ ./11-directories_permissions 
zakaria@ubuntu:/tmp/h$ ls -l
total 20
-rwxrwxr-x 1 zakaria zakaria   24 Sep 20 14:53 11-directories_permissions
drwx--x--x 2 zakaria zakaria 4096 Sep 20 14:49 dir0
drwx--x--x 2 zakaria zakaria 4096 Sep 20 14:49 dir1
drwx--x--x 2 zakaria zakaria 4096 Sep 20 14:49 dir2
-rw-rw-r-- 1 zakaria zakaria   23 Sep 20 14:25 hello
zakaria@ubuntu:/tmp/h$ 
```

#### 12. More directories
File: `12-directory_permissions`

Create a script that creates a directory called my_dir with permissions 751 in the working directory.
```
zakaria@ubuntu:/tmp/h$ ls -l
total 20
-rwxrwxr-x 1 zakaria zakaria   39 Sep 20 14:59 12-directory_permissions
drwx--x--x 2 zakaria zakaria 4096 Sep 20 14:49 dir0
drwx--x--x 2 zakaria zakaria 4096 Sep 20 14:49 dir1
drwx--x--x 2 zakaria zakaria 4096 Sep 20 14:49 dir2
-rw-rw-r-- 1 zakaria zakaria   23 Sep 20 14:25 hello
zakaria@ubuntu:/tmp/h$ ./12-directory_permission s
zakaria@ubuntu:/tmp/h$ ls -l
total 24
-rwxrwxr-x 1 zakaria zakaria   39 Sep 20 14:59 12-directory_permissions
drwx--x--x 2 zakaria zakaria 4096 Sep 20 14:49 dir0
drwx--x--x 2 zakaria zakaria 4096 Sep 20 14:49 dir1
drwx--x--x 2 zakaria zakaria 4096 Sep 20 14:49 dir2
drwxr-x--x 2 zakaria zakaria 4096 Sep 20 14:59 my_dir
-rw-rw-r-- 1 zakaria zakaria   23 Sep 20 14:25 hello
zakaria@ubuntu:/tmp/h$ 
```
#### 13. Change group
File: `13-change_group`

Write a script that changes the group owner to school for the file hello
```
zakaria@ubuntu:/tmp/h$ ls -l
total 24
-rwxrwxr-x 1 zakaria zakaria   34 Sep 20 15:03 13-change_group
drwx--x--x 2 zakaria zakaria 4096 Sep 20 14:49 dir0
drwx--x--x 2 zakaria zakaria 4096 Sep 20 14:49 dir1
drwx--x--x 2 zakaria zakaria 4096 Sep 20 14:49 dir2
drwxr-x--x 2 zakaria zakaria 4096 Sep 20 14:59 my_dir
-rw-rw-r-- 1 zakaria zakaria   23 Sep 20 14:25 hello
zakaria@ubuntu:/tmp/h$ sudo ./13-change_group 
zakaria@ubuntu:/tmp/h$ ls -l
total 24
-rwxrwxr-x 1 zakaria zakaria      34 Sep 20 15:03 13-change_group
drwx--x--x 2 zakaria zakaria    4096 Sep 20 14:49 dir0
drwx--x--x 2 zakaria zakaria    4096 Sep 20 14:49 dir1
drwx--x--x 2 zakaria zakaria    4096 Sep 20 14:49 dir2
drwxr-x--x 2 zakaria zakaria    4096 Sep 20 14:59 my_dir
-rw-rw-r-- 1 zakaria school   23 Sep 20 14:25 hello
zakaria@ubuntu:/tmp/h$ 
```

#### 14. Owner and group
File: `100-change_owner_and_group`

Write a script that changes the owner to vincent and the group owner to staff for all the files and directories in the working directory.
```
zakaria@ubuntu:/tmp/h$ ls -l
total 24
-rwxrwxr-x 1 zakaria zakaria   36 Sep 20 15:06 100-change_owner_and_group
drwx--x--x 2 zakaria zakaria 4096 Sep 20 14:49 dir0
drwx--x--x 2 zakaria zakaria 4096 Sep 20 14:49 dir1
drwx--x--x 2 zakaria zakaria 4096 Sep 20 14:49 dir2
drwxr-x--x 2 zakaria zakaria 4096 Sep 20 14:59 my_dir
-rw-rw-r-- 1 zakaria zakaria   23 Sep 20 14:25 hello
zakaria@ubuntu:/tmp/h$ sudo ./100-change_owner_and_group 
zakaria@ubuntu:/tmp/h$ ls -l
total 24
-rwxrwxr-x 1 vincent staff   36 Sep 20 15:06 100-change_owner_and_group
drwx--x--x 2 vincent staff 4096 Sep 20 14:49 dir0
drwx--x--x 2 vincent staff 4096 Sep 20 14:49 dir1
drwx--x--x 2 vincent staff 4096 Sep 20 14:49 dir2
drwxr-x--x 2 vincent staff 4096 Sep 20 14:59 my_dir
-rw-rw-r-- 1 vincent staff   23 Sep 20 14:25 hello
zakaria@ubuntu:/tmp/h$ 
```

#### 15. Symbolic links
File: `101-symbolic_link_permissions`

Write a script that changes the owner and the group owner of _hello to vincent and staff respectively.
```
zakaria@ubuntu:/tmp/h$ ls -l
total 24
-rwxrwxr-x 1 zakaria zakaria   44 Sep 20 15:12 101-symbolic_link_permissions
-rw-rw-r-- 1 zakaria zakaria   23 Sep 20 14:25 hello
lrwxrwxrwx 1 zakaria zakaria    5 Sep 20 15:10 _hello -> hello
zakaria@ubuntu:/tmp/h$ sudo ./101-symbolic_link_permissions 
zakaria@ubuntu:/tmp/h$ ls -l
total 24
-rwxrwxr-x 1 zakaria zakaria      44 Sep 20 15:12 101-symbolic_link_permissions
-rw-rw-r-- 1 zakaria zakaria      23 Sep 20 14:25 hello
lrwxrwxrwx 1 vincent  staff    5 Sep 20 15:10 _hello -> hello
zakaria@ubuntu:/tmp/h$ 
```

#### 16. If only
File: `102-if_only`

Write a script that changes the owner of the file hello to betty only if it is owned by the user guillaume.
```
zakaria@ubuntu:/tmp/h$ ls -l
total 24
-rwxrwxr-x 1 zakaria    zakaria      47 Sep 20 15:18 102-if_only 
-rw-rw-r-- 1 guillaume zakaria      23 Sep 20 14:25 hello
zakaria@ubuntu:/tmp/h$ sudo ./102-if_only 
zakaria@ubuntu:/tmp/h$ ls -l
total 24
-rwxrwxr-x 1 zakaria zakaria      47 Sep 20 15:18 102-if_only 
-rw-rw-r-- 1 betty  zakaria      23 Sep 20 14:25 hello
zakaria@ubuntu:/tmp/h$ 
```

#### 17. Star Wars
File: `103-Star_Wars` 

Write a script that will play the StarWars IV episode in the terminal.







