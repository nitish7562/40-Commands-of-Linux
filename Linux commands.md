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

**some common Vim commandsand shortcuts that are useful for editing text in the terminal**
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

### MKDIR command
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
