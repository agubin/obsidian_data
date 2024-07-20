позволяет рабоnать с csv, просматривая его по частям. Так же рассматривает обычный текстовый файл в котором один столбец это одна буква
```linux
agubin@DESKTOP-JD8OJJN:~/lsb$ cat file.txt
first line
second line
third line
fourth line
agubin@DESKTOP-JD8OJJN:~/lsb$ cut -c 1-5 file.txt
first
secon
third
fourt
agubin@DESKTOP-JD8OJJN:~/lsb$ cut -c 1 file.txt
f
s
t
f
```
