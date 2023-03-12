
Нужно войти:

```
sudo su 
# vi /etc/sudoers
```

пролистать вниз найти 

```
#User privilege specification

root     ALL=(ALL:ALL) ALL
```

и под root     ALL=(ALL:ALL) ALL  добавить username ALL=(ALL:ALL) ALL своего пользователя со всеми привилегиями

