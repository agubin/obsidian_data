просмотр истории команд

история хранится в файле ~/.bash_history

Что бы выполнить команду из списка можно использовать ее порядковый номер c !
```linux
!24
```

выполнить предыдущую команду !!
```linux
agubin@DESKTOP-JD8OJJN:~/lsb$ pwd
/home/agubin/lsb
agubin@DESKTOP-JD8OJJN:~/lsb$ !!
pwd
/home/agubin/lsb
```

повторить определенную команду с тем же списком аргументов что и прошлый раз. Необязательно что бы команды шли друг за другом.
```linux
agubin@DESKTOP-JD8OJJN:~/lsb$ du -sh /usr/bin/* | sort -h | less
agubin@DESKTOP-JD8OJJN:~/lsb$ pwd
/home/agubin/lsb
agubin@DESKTOP-JD8OJJN:~/lsb$ ls
user_ivan.txt  user_petr.txt  user_vasay.txt
agubin@DESKTOP-JD8OJJN:~/lsb$ cd ..
agubin@DESKTOP-JD8OJJN:~$ !du
du -sh /usr/bin/* | sort -h | less
agubin@DESKTOP-JD8OJJN:~$
```