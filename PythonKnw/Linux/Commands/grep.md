Искать рекурсивно(-r), регистронезависимо(-i), выводя номера строк(-n) в файлах с маской "\*.py", ищем "charset", в текущей директории
```shell
grep -rin --include="*.py" "charset" .
```

Так же можно что бы выводились строки до и после попадающей под шаблон
Флаг -A после(after), флаг -B до (before)

```shell
ip a | grep 192.168.* -A 3 -B 3
```