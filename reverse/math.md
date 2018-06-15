Математика
=========

* **Категория:** Reverse  
* **Стоимость:** 75  

### Описание  
Жаль, что флаг никуда не выводится...

### Что дается?  
Файл [rev](https://github.com/axelmaker/vkactf2018_writeup/raw/master/reverse/rev)

### Решение

Открываем файл через ```IDA Pro```  
Отображаем в декомпилированном виде:  

В первом цикле происходит ввод пользователя и записывается только 5 символов по адресу обозначаемому `v4` 
  
![alt text](https://github.com/axelmaker/vkactf2018_writeup/blob/master/reverse/reverse002.png?raw=true)

Далее видим, что введенную строку преобразуют в следующем цикле (каждый элемент меняется в зависимости от предыдущего а первый элемент строки перезаписывается).  

![alt text](https://github.com/axelmaker/vkactf2018_writeup/blob/master/reverse/reverse003.png?raw=true)

Следовательно введенная с клавиатуры строка не зависит от формирования пароля


Ставим точку прерывания  на строчку после выполнения цикла генерации пароля. Выполняем и смотрим значение в v4.  

![alt text](https://github.com/axelmaker/vkactf2018_writeup/blob/master/reverse/reverse004.png?raw=true)

Ответ: `FLAG{0A_O0A_O0A_O0A_O}`
