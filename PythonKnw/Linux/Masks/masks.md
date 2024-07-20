Создать 10 файлов с типовым именем
```linux
touch {1..10}.txt
```
```linux
agubin@DESKTOP-JD8OJJN:~$ ls
10.txt  1.txt  2.txt  3.txt  4.txt  5.txt  6.txt  7.txt  8.txt  9.txt  lsb  pyproj
```

Удалить все .txt файлы
```linux
rm *.txt
```

\* - это ноль или больше символов
? - это один символ
~ - это домашняя директория

Другие примеры
```linux
touch user_{ivan,petr,vasay}.txt
```
```linux
agubin@DESKTOP-JD8OJJN:~/lsb$ ls
user_ivan.txt  user_petr.txt  user_vasay.txt
```
