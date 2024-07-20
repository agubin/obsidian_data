показать статистику по файлу
Поле Access меняется при использовании файла
Поле Modify меняется при изменении контента этого файла
Поле Change меняется при изменении атрибутов файла
```linux
agubin@DESKTOP-JD8OJJN:~/lsb$ echo "content" > file.txt
agubin@DESKTOP-JD8OJJN:~/lsb$ stat file.txt
  File: file.txt
  Size: 8               Blocks: 8          IO Block: 4096   regular file
Device: 8,32    Inode: 30724       Links: 1
Access: (0644/-rw-r--r--)  Uid: ( 1000/  agubin)   Gid: ( 1000/  agubin)
Access: 2024-02-18 16:31:56.015369045 +0300
Modify: 2024-02-18 16:31:56.015369045 +0300
Change: 2024-02-18 16:31:56.015369045 +0300
 Birth: 2024-02-18 16:31:56.015369045 +0300
agubin@DESKTOP-JD8OJJN:~/lsb$ cat file.txt
content
agubin@DESKTOP-JD8OJJN:~/lsb$ stat file.txt
  File: file.txt
  Size: 8               Blocks: 8          IO Block: 4096   regular file
Device: 8,32    Inode: 30724       Links: 1
Access: (0644/-rw-r--r--)  Uid: ( 1000/  agubin)   Gid: ( 1000/  agubin)
Access: 2024-02-18 16:32:07.915368341 +0300
Modify: 2024-02-18 16:31:56.015369045 +0300
Change: 2024-02-18 16:31:56.015369045 +0300
 Birth: 2024-02-18 16:31:56.015369045 +0300
agubin@DESKTOP-JD8OJJN:~/lsb$ mv file.txt file1.txt
agubin@DESKTOP-JD8OJJN:~/lsb$ stat file1.txt
  File: file1.txt
  Size: 8               Blocks: 8          IO Block: 4096   regular file
Device: 8,32    Inode: 30724       Links: 1
Access: (0644/-rw-r--r--)  Uid: ( 1000/  agubin)   Gid: ( 1000/  agubin)
Access: 2024-02-18 16:32:07.915368341 +0300
Modify: 2024-02-18 16:31:56.015369045 +0300
Change: 2024-02-18 16:32:24.275367951 +0300
 Birth: 2024-02-18 16:31:56.015369045 +0300
agubin@DESKTOP-JD8OJJN:~/lsb$ echo "new content" >> file1.txt
agubin@DESKTOP-JD8OJJN:~/lsb$ stat file1.txt
  File: file1.txt
  Size: 20              Blocks: 8          IO Block: 4096   regular file
Device: 8,32    Inode: 30724       Links: 1
Access: (0644/-rw-r--r--)  Uid: ( 1000/  agubin)   Gid: ( 1000/  agubin)
Access: 2024-02-18 16:32:07.915368341 +0300
Modify: 2024-02-18 16:33:02.595367270 +0300
Change: 2024-02-18 16:33:02.595367270 +0300
 Birth: 2024-02-18 16:31:56.015369045 +0300
```