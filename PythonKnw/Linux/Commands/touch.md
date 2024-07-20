изменение атрибутов файла

Изменение временных меток
```linux
agubin@DESKTOP-JD8OJJN:~/lsb$ stat file2.txt
  File: file2.txt
  Size: 20              Blocks: 8          IO Block: 4096   regular file
Device: 8,32    Inode: 30724       Links: 1
Access: (0644/-rw-r--r--)  Uid: ( 1000/  agubin)   Gid: ( 1000/  agubin)
Access: 2024-02-18 16:32:07.915368341 +0300
Modify: 2024-02-18 16:33:02.595367270 +0300
Change: 2024-02-18 16:37:52.815369037 +0300
 Birth: 2024-02-18 16:31:56.015369045 +0300
agubin@DESKTOP-JD8OJJN:~/lsb$ touch -m --date="2004-05-06" file2.txt
agubin@DESKTOP-JD8OJJN:~/lsb$ touch -a --date="tomorrow" file2.txt
agubin@DESKTOP-JD8OJJN:~/lsb$ stat file2.txt
  File: file2.txt
  Size: 20              Blocks: 8          IO Block: 4096   regular file
Device: 8,32    Inode: 30724       Links: 1
Access: (0644/-rw-r--r--)  Uid: ( 1000/  agubin)   Gid: ( 1000/  agubin)
Access: 2024-02-19 16:51:36.916420772 +0300
Modify: 2004-05-06 00:00:00.000000000 +0400
Change: 2024-02-18 16:51:36.905363260 +0300
 Birth: 2024-02-18 16:31:56.015369045 +0300
```
