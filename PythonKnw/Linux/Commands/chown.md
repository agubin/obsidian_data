Сменить владельца файла
```shell
sudo chown some_user some_file
```

Также можно сменить и владельца и группу:
```shell
sudo chown some_user:some_group some_file
```
Сменить только группу:
```shell
sudo chown :some_group some_file
```
Сменить пользователя и установить группу на его основную
```shell
sudo chown some_user: some_file
```
