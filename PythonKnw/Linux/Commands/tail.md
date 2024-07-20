позволяет просмотреть последние n строк файла
```linux
agubin@DESKTOP-JD8OJJN:~/lsb$ cat file.txt
first line
second line
third line
fourth line
agubin@DESKTOP-JD8OJJN:~/lsb$ tail -n1 file.txt
fourth line
agubin@DESKTOP-JD8OJJN:~/lsb$ tail -n3 file.txt
second line
third line
fourth line
```
