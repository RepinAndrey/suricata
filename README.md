# Домашнее задание к занятию "`Защита хоста`" - `Репин Андрей`


### Задание 1

1. Установите eCryptfs.
2. Добавьте пользователя cryptouser.

![img](https://github.com/RepinAndrey/HostProtection/blob/main/img/AddCryptouser.png)

3. Зашифруйте домашний каталог пользователя с помощью eCryptfs.

![img](https://github.com/RepinAndrey/HostProtection/blob/main/img/CryptHome.png)


### Задание 2

1. Установите поддержку LUKS.

![img](https://github.com/RepinAndrey/HostProtection/blob/main/img/CryptSetup.png)


2. Создайте небольшой раздел, например, 100 Мб.

![img](https://github.com/RepinAndrey/HostProtection/blob/main/img/disk.png)

3. Зашифруйте созданный раздел с помощью LUKS.

Подготовка раздела

![img](https://github.com/RepinAndrey/HostProtection/blob/main/img/Prepare.png)

Монтирование раздела

![img](https://github.com/RepinAndrey/HostProtection/blob/main/img/Mount.png)

Форматирование раздела

![img](https://github.com/RepinAndrey/HostProtection/blob/main/img/Format.png)

МОнтирование "открытого раздела"

![img](https://github.com/RepinAndrey/HostProtection/blob/main/img/MountSecret.png)

Завершение работы

![img](https://github.com/RepinAndrey/HostProtection/blob/main/img/Umount.png)



