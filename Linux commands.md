# 40 commands of Linux
![image](https://media.geeksforgeeks.org/wp-content/uploads/s2-1.jpg)

## File and Folder Create Command 
### 1. Touch Command
* touch command is a used to create a new empty files
```bash
touch FileName
```
```bash
nitishkumar@nitishkumar-IdeaPad-3-15ITL6:~/Documents$ ls
nitishkumar@nitishkumar-IdeaPad-3-15ITL6:~/Documents$ touch file1
nitishkumar@nitishkumar-IdeaPad-3-15ITL6:~/Documents$ ls
file1
```

**With the help of touch command we can also create multifile at once**
```bash
nitishkumar@nitishkumar-IdeaPad-3-15ITL6:~/Documents$ touch file1 file2 file3 file4
nitishkumar@nitishkumar-IdeaPad-3-15ITL6:~/Documents$ ls
file1  file2  file3  file4
```

**`touch` command also used for to change the timestamps of existing files.**
**A timestamp is a information associated witha file that identifies an important time in the file's history**
* Access time: The last time the file was read
* Modification time: The last time the contents of the file were modified
* Change time: The last time the file's metadata was changed

```bash
nitishkumar@nitishkumar-IdeaPad-3-15ITL6:~/Documents$ stat file1
  File: file1
  Size: 0         	Blocks: 0          IO Block: 4096   regular empty file
Device: 10302h/66306d	Inode: 11151124    Links: 1
Access: (0664/-rw-rw-r--)  Uid: ( 1000/nitishkumar)   Gid: ( 1000/nitishkumar)
Access: 2024-06-18 20:36:17.695801603 +0530
Modify: 2024-06-18 20:36:17.695801603 +0530
Change: 2024-06-18 20:36:17.695801603 +0530
 Birth: 2024-06-18 20:36:17.695801603 +0530
```

**-m is used to change the modification time and -a option is used to change the access time**
```bash
touch -m file1
```
```bash
nitishkumar@nitishkumar-IdeaPad-3-15ITL6:~/Documents$ touch -m file1
nitishkumar@nitishkumar-IdeaPad-3-15ITL6:~/Documents$ stat file1
  File: file1
  Size: 0         	Blocks: 0          IO Block: 4096   regular empty file
Device: 10302h/66306d	Inode: 11151124    Links: 1
Access: (0664/-rw-rw-r--)  Uid: ( 1000/nitishkumar)   Gid: ( 1000/nitishkumar)
Access: 2024-06-18 21:25:17.761273922 +0530
Modify: 2024-06-18 21:27:00.330488562 +0530
Change: 2024-06-18 21:27:00.330488562 +0530
 Birth: 2024-06-18 20:36:17.695801603 +0530
```

```bash
touch -a file1
```
```bash
nitishkumar@nitishkumar-IdeaPad-3-15ITL6:~/Documents$ touch -a file1
nitishkumar@nitishkumar-IdeaPad-3-15ITL6:~/Documents$ stat file1
  File: file1
  Size: 0         	Blocks: 0          IO Block: 4096   regular empty file
Device: 10302h/66306d	Inode: 11151124    Links: 1
Access: (0664/-rw-rw-r--)  Uid: ( 1000/nitishkumar)   Gid: ( 1000/nitishkumar)
Access: 2024-06-18 21:25:17.761273922 +0530
Modify: 2024-06-18 20:36:17.695801603 +0530
Change: 2024-06-18 21:25:17.761273922 +0530
 Birth: 2024-06-18 20:36:17.695801603 +0530
```

**If we want to set the modify timestamp then we can use `touch -d` command
```bash
nitishkumar@nitishkumar-IdeaPad-3-15ITL6:~$ touch -d "2024-06-19 10:54" file1
nitishkumar@nitishkumar-IdeaPad-3-15ITL6:~$ stat file1
  File: file1
  Size: 0         	Blocks: 0          IO Block: 4096   regular empty file
Device: 10302h/66306d	Inode: 11147913    Links: 1
Access: (0664/-rw-rw-r--)  Uid: ( 1000/nitishkumar)   Gid: ( 1000/nitishkumar)
Access: 2024-06-19 10:54:00.000000000 +0530
Modify: 2024-06-19 10:54:00.000000000 +0530
Change: 2024-06-19 10:54:06.044621694 +0530
 Birth: 2024-06-19 10:54:06.044621694 +0530
```

### 2. vim command
* `vim` command is an editor to create or edit a text file. It is used to open a file in vim editor
```bash
vim filename
```

```bash
nitishkumar@nitish:~/Documents$ vim file1

Hello nitish
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
"file1" 2L, 14B                                               2,12          All

```

**some common Vim commands and shortcuts that are useful for editing text in the terminal**
1. Save the file (write).
```bash
:w
```
2. Quit Vim editor.
```bash
:q
```
3. Save and quit Vim editor
```bash
:wq or :x
```
4.  Quit without saving.
```bash
:q!
```

### 3. MKDIR Command
* `mkdir` (make directory) command used for creating a new directories.
```bash
mkdir directory_name
```

```bash
nitishkumar@nitish:~/Documents$ mkdir new_directory
nitishkumar@nitish:~/Documents$ ls
new_directory
```

**we can create multiple directory at once**
```bash
mkdir dir1 dir2 dir3 dir4
```

```bash
nitishkumar@nitish:~/Documents$ mkdir dir1 dir2 dir3 dir4
nitishkumar@nitish:~/Documents$ ls
dir1  dir2  dir3  dir4  new_directory
```

## File and Folder Permission command
### 1. CHOWN Command
* `chown` command is a change ownership command. We can change ownership of any file or directory with the help of `chown` command.
```bash
sudo chown -c new_owner file/directory name
```

* Note: `Remember, ownership can be changed only by the person who created the file or directory.`

### 2. CHGRP Command
* `chgrp` command used for change group of any file or directory. We can change group of any file or directory with the help of `chgrp` command.
```bash
sudo chgrp -c new_groupname file/directory name
```
### 3. CHMOD Command
* `chmod` (change mode) command is used to change the file system modes/permissions of files and directories.

**Types of permission**
  1. r: read 
  2. w: write 
  3. x: execute

**Permissions (rwx) levels:**
u- Yourself (current user)
g- group in which user belongs to
o- others
a- all

**How to see the permissions**
```bash
ls -l or ls -ltr
```

```bash
nitishkumar@nitish:~$ ls -ltr
total 282412
-rwxr-xr-x   1 nitishkumar nitishkumar  11894416 Jul 18  2021  chromedriver
-rw-r--r--   1 nitishkumar nitishkumar    326542 May 27  2023  LICENSE.chromedriver
drwxr-xr-x   2 nitishkumar nitishkumar      4096 Feb 22 17:40  Videos
drwxr-xr-x   2 nitishkumar nitishkumar      4096 Feb 22 17:40  Templates
drwxr-xr-x   2 nitishkumar nitishkumar      4096 Feb 22 17:40  Music
-rw-rw-r--   1 nitishkumar nitishkumar 167613956 Mar 12 16:27  jdk-22_linux-x64_bin.deb
-rw-rw-r--   1 nitishkumar nitishkumar        68 Apr  3 11:55  bash.bashrc
-rw-r--r--   1 root        root              233 Apr 19 16:06  1
-rw-r--r--   1 root        root              233 Apr 20 10:40 '\'
-rw-r--r--   1 root        root                0 Apr 25 18:00  Mongodb
drwxrwxr-x   3 nitishkumar nitishkumar      4096 May 21 12:01  Postman
drwxr-xr-x   3 nitishkumar nitishkumar      4096 Jun 15 10:19  Pictures
drwxrwxr-x   4 nitishkumar nitishkumar      4096 Jun 21 00:16  mernstack_chat
-rw-rw-r--   1 nitishkumar nitishkumar       268 Jun 21 20:05  package.json
drwxrwxr-x 505 nitishkumar nitishkumar     20480 Jun 21 20:05  node_modules
-rw-rw-r--   1 nitishkumar nitishkumar    486823 Jun 21 20:05  package-lock.json
-rw-rw-r--   1 nitishkumar nitishkumar 108773084 Jun 22 07:29  google-chrome-stable_current_amd64.deb
drwxrwxr-x   3 nitishkumar nitishkumar      4096 Jun 24 21:05  eclipse
drwx------   8 nitishkumar nitishkumar      4096 Jun 24 23:18  snap
drwxrwxr-x   6 nitishkumar nitishkumar      4096 Jun 25 00:48  eclipse-workspace
drwxr-xr-x  10 nitishkumar nitishkumar      4096 Jul  2 16:33  Downloads
drwxr-xr-x  11 nitishkumar nitishkumar      4096 Jul  2 23:11  Desktop
drwxr-xr-x   7 nitishkumar nitishkumar      4096 Jul  2 23:15  Documents
```

**Command of change permission**
```bash
chmod u+r filename (For adding permission)
chmod u-r filename (For removing permission)
```

```bash
chmod ugo+r filename
chmod ugo-r filename
```

```bash
chmod a+rwx filename (adding permission for all)
```
* Note: `Remember, Only its owner can change the permission of the file except root user. Because root user can change permission of any file or directories.`

**Example**
* In this example we remove write (w)permission for current user
```bash
nitishkumar@nitish:~/Documents$ ls -l
total 4
drwxrwxr-x 2 nitishkumar nitishkumar 4096 Jul  2 23:12 new_directory
nitishkumar@nitish:~/Documents$ chmod u-w new_directory
nitishkumar@nitish:~/Documents$ ls -l
total 4
dr-xrwxr-x 2 nitishkumar nitishkumar 4096 Jul  2 23:12 new_directory

```

* In this Example we remove read (r)permission for others
```bash
nitishkumar@nitish:~/Documents$ chmod o-r new_directory
nitishkumar@nitish:~/Documents$ ls -l
total 4
dr-xrwx--x 2 nitishkumar nitishkumar 4096 Jul  2 23:12 new_directory
```

## Check File/Folder/Content command
### 1. ls command
* `ls` is a shell linux command in linux. It is used to obtain a list of all filesname in a current directory.

**ls options**
1. `ls -a` (all)- It is used for list all files including hidden files.
2. `ls -s` (size)- It is used for list the biggest files first
3. `ls -l` (long)- List all the attributes of all files in the current directory including(type, size, ownership, permissions)
4. `ls -r` (reverse)- It is used for reverse the files in sort order
5. `ls -t` (time)- It is used for presents the files in the order of their modification time, the last modified placed first.

### 2. ll command
* `ll` command stands for long list files. `ll` command lists the files and directories in our current directory in a long format, providing detailed information such as file permissions, number of links, owner, group, size, and time of last modification .

### 3. cat command
* `cat` commmand is used for create files, concatinate more files together and also we can merge more than one file in a single files.
* Other features of `cat` command is that we can read the contents of a file.

**Create a file**
```bash
cat>testfile.txt
```

```bash
nitishkumar@nitish:~$ cat>testfile.txt
This is a testfile
```

**Read the file of content**
```bash
nitishkumar@nitish:~$ cat testfile.txt
This is a testfile
```

**Concatinate the files**
```bash
nitishkumar@nitish:~$ cat testfile.txt>>testfile2.txt
nitishkumar@nitish:~$ cat testfile2.txt
This is a testfile2
This is a testfile
```

**Merge files contents in an another files.
```bash
nitishkumar@nitish:~$ cat>testfile3.txt
nitishkumar@nitish:~$ cat testfile.txt testfile2.txt > testfile3.txt
nitishkumar@nitish:~$ cat testfile3.txt
This is a testfile
This is a testfile2
This is a testfile
```
### 4. GREP Command
* grep stands for `Global Regular Expression Print`
* `grep` command is used for search a particular string or keyword from a file and prints lines matching a pattern.
* It check line by line and print lines matching given pattern.
* we can use `grep` command anywhere like with files, searchiing for a file, directories etc.

```bash
grep String_name/keyword_name filename
```
Note: `grep command is a case sensitive command`
* For ignoring case sensative we can use `-i` command.

```bash
grep -i String_name/keyword_name filename
```

```bash
nitishkumar@nitish:~$ cat testfile.txt
This is a testfile
nitishkumar@nitish:~$ grep This testfile.txt
*This* is a testfile
nitishkumar@nitish:~$ grep this testfile.txt
nitishkumar@nitish:~$ grep -i this testfile.txt
*This* is a testfile
```

### 5. HEAD Command
* `head` command is used to display the first few line of a text file.
* By default it shows first 10 lines of the file but we can specify a different number of a lines using the `-n` option.

```bash
nitishkumar@nitish:~$ head testfile.txt
Bihar
Hariyana
Uttar pradesh
jammu Kashmir
Jharkhand
Odisha
Rajasthan
Goa
Karnataka
Tamilnadu
```
**For specify a number**
```bash
head -n number file_name
```

```bash
nitishkumar@nitish:~$ head -n 5 testfile.txt
Bihar
Hariyana
Uttar pradesh
jammu Kashmir
Jharkhand
```

### 6. TAIL Command
* The `tail` command is countered part to `head` command. It is used to display the last few lines of a text file.
* By default it shows last 10 lines of the file but we can specify a different number of lines with the `-n` option.

```bash
nitishkumar@nitish:~$ tail testfile.txt
Tripura
Nagaland
Madhya Pradesh
Chhatisgarh
Manipur
Himachal Pradesh
Maharastra
Arunachal Pradesh		
Mizoram		
Assam
```

**For specify a number**
```bash
nitishkumar@nitish:~$ tail -n 5 testfile.txt
Himachal Pradesh
Maharastra
Arunachal Pradesh		
Mizoram		
Assam
```

Note: `Both head and tail are handy for quickly inspecting the beginning or end of a file, especially when dealing with log files, Large documents, or any text file with a significant amount of content.`

### 7. Less Command
* `less` command is used to display a contents of a file in an orgnizes way.
* `less` command allow us to navigate forwards and backwards through the file,

```bash
less file_name
```

**We can control the navigation with the help of key.**
1. `q`: For quit the page.
2. `space`: for Scroll down one page.
3. `b`: scroll up one page.
4. `enter`: scroll down one line.
5. `k`: scroll up one line.
