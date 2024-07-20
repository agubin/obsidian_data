используется для конкатенации потоков вывода. Команды tac выводим наоборот

```linux
agubin@DESKTOP-JD8OJJN:~/lsb$ printf "firstline\nsecond line\nthird line\n" > 1.txt
agubin@DESKTOP-JD8OJJN:~/lsb$ cat 1.txt
firstline
second line
third line
agubin@DESKTOP-JD8OJJN:~/lsb$ tac 1.txt
third line
second line
firstline
agubin@DESKTOP-JD8OJJN:~/lsb$ printf "first file\n" > first.txt
agubin@DESKTOP-JD8OJJN:~/lsb$ printf "second file\n" > second.txt
agubin@DESKTOP-JD8OJJN:~/lsb$ cat first.txt second.txt
first file
second file
agubin@DESKTOP-JD8OJJN:~/lsb$ cat first.txt 1.txt
first file
firstline
second line
third line
agubin@DESKTOP-JD8OJJN:~/lsb$ tac first.txt 1.txt
first file
third line
second line
firstline
```

