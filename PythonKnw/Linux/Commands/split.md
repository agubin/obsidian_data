Разбить файл на блоки 
```shell
split -b 20M splitted_file "block_prefix."
```

Собрать файлы
```shell
cat block_prefix.* > catted_file_name
```
