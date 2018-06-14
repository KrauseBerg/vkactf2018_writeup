Разогрев
=========

* **Категория:** Reverse  
* **Стоимость:** 10  

### Описание  
Just do it!

### Что дается?  
Файл [re1](https://github.com/axelmaker/vkactf2018_writeup/raw/master/reverse/re1)

### Решение

Открываем файл через ```IDA Pro```  
Отображаем в декомпилированном виде:  
![alt text](https://github.com/axelmaker/vkactf2018_writeup/blob/master/reverse/reverse001.png?raw=true)

Сразу бросается в глаза функция ```strcmp(s1,”#E4syRE#”)```.  
Как видно выше s1 вводится с клавиатуры  
Ответ:  ```FLAG{#E4syRE#}```
