# «Домашнее задание к занятию «Защита хоста»» - Грибова Анастасия

### Задание 1

1. Установите **eCryptfs**.
2. Добавьте пользователя cryptouser.
3. Зашифруйте домашний каталог пользователя с помощью eCryptfs.
   
```
sudo apt install ecryptfs-utils
```
```
sudo adduser cryptouser
```

![Название скриншота 1](https://github.com/gribova-anastasia/13-2/blob/0798a3f0c86a60369d46d00d7e77a13389bf1889/1.png)
![Название скриншота 2](https://github.com/gribova-anastasia/13-2/blob/0798a3f0c86a60369d46d00d7e77a13389bf1889/2.png)





### Задание 2

1. Установите поддержку **LUKS**.
2. Создайте небольшой раздел, например, 100 Мб.
3. Зашифруйте созданный раздел с помощью LUKS.

![Название скриншота 3](https://github.com/gribova-anastasia/13-2/blob/ea8cc923d5eb7c0578f3f8aaedadfcf1326cb35b/3.png)
![Название скриншота 4](https://github.com/gribova-anastasia/13-2/blob/ea8cc923d5eb7c0578f3f8aaedadfcf1326cb35b/4.png)
![Название скриншота 5](https://github.com/gribova-anastasia/13-2/blob/ea8cc923d5eb7c0578f3f8aaedadfcf1326cb35b/5.png)
![Название скриншота 6](https://github.com/gribova-anastasia/13-2/blob/ea8cc923d5eb7c0578f3f8aaedadfcf1326cb35b/6.png)
![Название скриншота 7](https://github.com/gribova-anastasia/13-2/blob/ea8cc923d5eb7c0578f3f8aaedadfcf1326cb35b/7.png)
![Название скриншота 8](https://github.com/gribova-anastasia/13-2/blob/ea8cc923d5eb7c0578f3f8aaedadfcf1326cb35b/8.png)

```
sudo dd if=/dev/zero of=/dev/mapper/cryptodisk
```

```
sudo mkfs.ext4 /dev/mapper/cryptodisk
```

```
mkdir .secret
```
```
sudo mount /dev/mapper/cryptodisk .secret/
```

```
sudo umount .secret
```

```
sudo cryptsetup luksClose cryptodisk
```
