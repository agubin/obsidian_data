Пример
```shell
chmod 0+r some_file
```
Структура команды
```shell
chmod <target><change><mods> <file_name>
```
target - для кого меняются права
- u - владелец файла
- g - группа владеющая файлом
- o - остальные
change - изменения:
- + - добавить права
- - \- убрать права
mods - права:
- r - чтение
- w - запись
- x - исполнение

Примеры команд

```shell
agubin@DESKTOP-JD8OJJN:/tmp$ ls -l hello.txt buy.txt
-rw-r--r-- 1 agubin agubin  4 Feb 22 22:18 buy.txt
-rw-r----- 1 agubin friends 6 Feb 22 21:47 hello.txt
agubin@DESKTOP-JD8OJJN:/tmp$ chmod o+w hello.txt buy.txt
agubin@DESKTOP-JD8OJJN:/tmp$ ls -l hello.txt buy.txt
-rw-r--rw- 1 agubin agubin  4 Feb 22 22:18 buy.txt
-rw-r---w- 1 agubin friends 6 Feb 22 21:47 hello.txt
agubin@DESKTOP-JD8OJJN:/tmp$ chmod g+w o-w hello.txt
chmod: cannot access 'o-w': No such file or directory
agubin@DESKTOP-JD8OJJN:/tmp$ chmod o-rwx buy.txt
agubin@DESKTOP-JD8OJJN:/tmp$ ls -l hello.txt buy.txt
-rw-r----- 1 agubin agubin  4 Feb 22 22:18 buy.txt
-rw-rw--w- 1 agubin friends 6 Feb 22 21:47 hello.txt
```

Побитовые опции:
![[Pasted image 20240222225054.png]]

```shell
sudo chmod 714 some_file
```
эквивалентно установке -rwx--xr--
