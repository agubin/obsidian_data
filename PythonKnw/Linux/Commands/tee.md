То что поступает на вход этой команды отправляется в стандартный вывод и в файл
```linux
agubin@DESKTOP-JD8OJJN:~/lsb$ ll ~/lsb | tee home_ctlg.txt
total 24
drwxr-xr-x 2 agubin agubin 4096 Feb 17 22:19 .
drwx------ 6 agubin agubin 4096 Feb 17 21:51 ..
-rw-r--r-- 1 agubin agubin   33 Feb 17 21:51 1.txt
-rw-r--r-- 1 agubin agubin   11 Feb 17 21:52 first.txt
-rw-r--r-- 1 agubin agubin  840 Feb 17 22:19 home_ctg.txt
-rw-r--r-- 1 agubin agubin    0 Feb 17 22:19 home_ctlg.txt
-rw-r--r-- 1 agubin agubin   12 Feb 17 21:52 second.txt
agubin@DESKTOP-JD8OJJN:~/lsb$ cat home_ctlg.txt
total 24
drwxr-xr-x 2 agubin agubin 4096 Feb 17 22:19 .
drwx------ 6 agubin agubin 4096 Feb 17 21:51 ..
-rw-r--r-- 1 agubin agubin   33 Feb 17 21:51 1.txt
-rw-r--r-- 1 agubin agubin   11 Feb 17 21:52 first.txt
-rw-r--r-- 1 agubin agubin  840 Feb 17 22:19 home_ctg.txt
-rw-r--r-- 1 agubin agubin    0 Feb 17 22:19 home_ctlg.txt
-rw-r--r-- 1 agubin agubin   12 Feb 17 21:52 second.txt
agubin@DESKTOP-JD8OJJN:~/lsb$
```

