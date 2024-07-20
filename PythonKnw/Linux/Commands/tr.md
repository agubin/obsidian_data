Переводит одни символы в другие
```linux
agubin@DESKTOP-JD8OJJN:~/lsb$ echo $PATH
/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/usr/lib/wsl/lib:/mnt/c/Windows/system32:/mnt/c/Windows:/mnt/c/Windows/System32/Wbem:/mnt/c/Windows/System32/WindowsPowerShell/v1.0/:/mnt/c/Windows/System32/OpenSSH/:/mnt/c/Users/agubin/.jdks/liberica-21.0.2/bin:/mnt/c/Users/agubin/AppData/Local/Microsoft/WindowsApps:/mnt/c/Users/agubin/AppData/Local/Programs/Microsoft VS Code/bin
agubin@DESKTOP-JD8OJJN:~/lsb$ echo $PATH | tr ":" "\n"
/usr/local/sbin
/usr/local/bin
/usr/sbin
/usr/bin
/sbin
/bin
/usr/games
/usr/local/games
/usr/lib/wsl/lib
/mnt/c/Windows/system32
/mnt/c/Windows
/mnt/c/Windows/System32/Wbem
/mnt/c/Windows/System32/WindowsPowerShell/v1.0/
/mnt/c/Windows/System32/OpenSSH/
/mnt/c/Users/agubin/.jdks/liberica-21.0.2/bin
/mnt/c/Users/agubin/AppData/Local/Microsoft/WindowsApps
/mnt/c/Users/agubin/AppData/Local/Programs/Microsoft VS Code/bin
```
