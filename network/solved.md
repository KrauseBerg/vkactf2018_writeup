Разогрев [Network 10]
================
> А ты умеешь запускать wireshark?
Файл: [network.pcapng](https://github.com/axelmaker/vkactf2018_writeup/raw/master/network/network.pcapng)

Используя ```Wireshark``` открываем дамп.  
Первым делом смотрим объекты ```HTTP```.  
Переходим:  
```File > Export Objects > HTTP```  
Сохраняем файлы с пакетов, просматриваем их и обнаруживаем флаг  
![alt text](https://github.com/axelmaker/vkactf2018_writeup/blob/master/network/123.jpg?raw=true)


Один за другим  [Network 25]
================
> В этом дампе есть что-то интересное.  
Возможно тебе пригодится ASCII-таблица
Файл: [network2.pcapng](https://github.com/axelmaker/vkactf2018_writeup/raw/master/network/network2.pcapng)

Используя ```Wireshark``` открываем дамп.  
Смотрим объекты ```HTTP```.  
Переходим:  
```File > Export Objects > HTTP```  
Как видно, нам сразу в глаза бросается флаг)  
![alt text](https://github.com/axelmaker/vkactf2018_writeup/blob/master/network/network2.png?raw=true)  
>```flag{http_never_die}```


Я есть брут [Network 30]
================
> О нет! Кто-то брутит мой сайт!  
Файл: [network3.pcapng](https://github.com/axelmaker/vkactf2018_writeup/raw/master/network/network3.pcapng)

Используя ```Wireshark``` открываем дамп.
Понимаем, что пытались залогиниться, поэтому смотрим объекты ```HTTP```.  
Видим 4 попытки зайти на сайт под ```Admin```  
Просматриваем их пакеты, и в одном из них находим флаг.  

> ```FLAG{bru73f0rc3_4dm1n}```


Время жизни [Network 40]
================
> Файл: [network4.pcapng](https://github.com/axelmaker/vkactf2018_writeup/raw/master/network/network4.pcapng)

Используя ```Wireshark``` открываем дамп.  
Ставим фильтр на протокол ```ICMP```.  
По названию таска, понимаем, что нужно смотреть на ```TTL (Time to live)```.
Сортируем по времени и в каждом пакете находим по 1 символу флага.  

>```flag{tl_is_]ood!}```
