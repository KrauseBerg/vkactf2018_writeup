Строки
=========

* **Категория:** Reverse  
* **Стоимость:** 15  

### Описание  
Попробуйте найти флаг.

### Что дается?  
Файл [elf.bin](https://github.com/axelmaker/vkactf2018_writeup/raw/master/reverse/elf.bin)

### Решение

Открываем файл через ```IDA Pro```  
Отображаем в декомпилированном виде:  

![alt text](https://github.com/axelmaker/vkactf2018_writeup/blob/master/reverse/reverse005.png?raw=true)

Кроме функции `puts()` в файле больше ничего не наблдюдаем.  
Отображаем строки:  

![alt text](https://github.com/axelmaker/vkactf2018_writeup/blob/master/reverse/reverse006.png?raw=true)

Флаг: `flag{c_strings_so_easy}`

