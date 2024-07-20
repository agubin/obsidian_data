```
ls -R <path>
```
рекурсивно показать содержимое папок

управление временной меткой в выводе. По умолчанию показывается Modify, см. [[stat]]
```linux
stat file2.txt
  File: file2.txt
  Size: 20              Blocks: 8          IO Block: 4096   regular file
Device: 8,32    Inode: 30724       Links: 1
Access: (0644/-rw-r--r--)  Uid: ( 1000/  agubin)   Gid: ( 1000/  agubin)
Access: 2024-02-18 16:32:07.915368341 +0300
Modify: 2024-02-18 16:33:02.595367270 +0300
Change: 2024-02-18 16:37:52.815369037 +0300
 Birth: 2024-02-18 16:31:56.015369045 +0300
agubin@DESKTOP-JD8OJJN:~/lsb$ ll file2.txt
-rw-r--r-- 1 agubin agubin 20 Feb 18 16:33 file2.txt
agubin@DESKTOP-JD8OJJN:~/lsb$ ll --time=atime file2.txt
-rw-r--r-- 1 agubin agubin 20 Feb 18 16:32 file2.txt
agubin@DESKTOP-JD8OJJN:~/lsb$ ll --time=ctime file2.txt
-rw-r--r-- 1 agubin agubin 20 Feb 18 16:37 file2.txt
agubin@DESKTOP-JD8OJJN:~/lsb$ ll --time=birth file2.txt
-rw-r--r-- 1 agubin agubin 20 Feb 18 16:31 file2.txt
agubin@DESKTOP-JD8OJJN:~/lsb$ ll --time-style=full-iso file2.txt
-rw-r--r-- 1 agubin agubin 20 2024-02-18 16:33:02.595367270 +0300 file2.txt
```
