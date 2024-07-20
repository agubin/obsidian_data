удалить файл(ы)
```linux
agubin@DESKTOP-JD8OJJN:~/lsb$ ll
total 28
drwxr-xr-x 2 agubin agubin 4096 Feb 17 22:19 .
drwx------ 6 agubin agubin 4096 Feb 17 21:51 ..
-rw-r--r-- 1 agubin agubin   33 Feb 17 21:51 1.txt
-rw-r--r-- 1 agubin agubin   11 Feb 17 21:52 first.txt
-rw-r--r-- 1 agubin agubin  840 Feb 17 22:19 home_ctg.txt
-rw-r--r-- 1 agubin agubin  383 Feb 17 22:19 home_ctlg.txt
-rw-r--r-- 1 agubin agubin   12 Feb 17 21:52 second.txt
agubin@DESKTOP-JD8OJJN:~/lsb$ rm *.txt
agubin@DESKTOP-JD8OJJN:~/lsb$ ll
total 8
drwxr-xr-x 2 agubin agubin 4096 Feb 17 22:28 .
drwx------ 6 agubin agubin 4096 Feb 17 21:51 ..
```
удалить директорию
```linux
agubin@DESKTOP-JD8OJJN:~/lsb$ ll
total 12
drwxr-xr-x 3 agubin agubin 4096 Feb 17 22:29 .
drwx------ 6 agubin agubin 4096 Feb 17 21:51 ..
drwxr-xr-x 2 agubin agubin 4096 Feb 17 22:29 somefolder
agubin@DESKTOP-JD8OJJN:~/lsb$ rm -r somefolder
agubin@DESKTOP-JD8OJJN:~/lsb$ ll
total 8
drwxr-xr-x 2 agubin agubin 4096 Feb 17 22:30 .
drwx------ 6 agubin agubin 4096 Feb 17 21:51 ..
```

