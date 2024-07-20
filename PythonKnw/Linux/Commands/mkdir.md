создать директорию
```linux
agubin@DESKTOP-JD8OJJN:~/lsb$ mkdir somefolder
agubin@DESKTOP-JD8OJJN:~/lsb$ ll
total 12
drwxr-xr-x 3 agubin agubin 4096 Feb 17 22:29 .
drwx------ 6 agubin agubin 4096 Feb 17 21:51 ..
drwxr-xr-x 2 agubin agubin 4096 Feb 17 22:29 somefolder
```

другой пример
```linux
agubin@DESKTOP-JD8OJJN:~/lsb$ mkdir -p somefolder/{one,two}/inner
agubin@DESKTOP-JD8OJJN:~/lsb$ tree somefolder/
somefolder/
├── one
│   └── inner
└── two
    └── inner

5 directories, 0 files
```
