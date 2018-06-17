Жестокая жесть
=========

* **Категория:** Reverse  
* **Стоимость:** 150  

### Описание  
Здесь вас вообще ничего не спасет.

### Что дается?  
Файл [re4](https://github.com/axelmaker/vkactf2018_writeup/raw/master/reverse/re4)

### Решение

Открываем файл через ```IDA Pro```  
Отображаем в декомпилированном виде:  

![alt text](https://github.com/axelmaker/vkactf2018_writeup/blob/master/reverse/reverse007.png?raw=true)

В функции `strcmp` наблюдаем сравнение строк с `md5`.  
Расшифруем с помощью любого Decrypter`a.  

`365d38c60c4e98ca5ca6dbc02d396e53 MD5 : password12345`  

Флаг: `FLAG{password12345}`
