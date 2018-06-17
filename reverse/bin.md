Жесть...
=========

* **Категория:** Reverse  
* **Стоимость:** 150  

### Описание  
Отладчик вас не спасет.

### Что дается?  
Файл [bin](https://github.com/axelmaker/vkactf2018_writeup/raw/master/reverse/bin)

### Решение

Открываем файл через ```IDA Pro```  
Отображаем в декомпилированном виде:  

  
![alt text](https://github.com/axelmaker/vkactf2018_writeup/blob/master/reverse/reverse008.png?raw=true)
![alt text](https://github.com/axelmaker/vkactf2018_writeup/blob/master/reverse/reverse009.png?raw=true)
![alt text](https://github.com/axelmaker/vkactf2018_writeup/blob/master/reverse/reverse010.png?raw=true)

Первый цикл ожидает ввода 22 символов и Enter. Данная строка записывается по адресу `v11`.  
Следующая часть кода изменяет входную строку а именно `(xor с 66h +108h-103h)`  и затем к каждому символу прибавляется определенное число.  
В конце измененная строка побайтово сравнивается с `v4 v5 v6 v7 v8 v9` (int лежащие друг за другом в памяти) и если результаты совпадает то `WIN`  

![alt text](https://github.com/axelmaker/vkactf2018_writeup/blob/master/reverse/reverse011.png?raw=true)

 Пишем программу для нахождения пароля(в обратную сторону).  
 Для этого посмотрим на конечный пароль:  

![alt text](https://github.com/axelmaker/vkactf2018_writeup/blob/master/reverse/reverse012.png?raw=true)

Используя конечную строку и алгоритм кода, получаем программу:  

``` python

ctrl = [0x21, 0x79, 0x65, 0x61, 0x68, 0x5f, 0x72, 0x65, 0x76, 0x65, 0x72, 
        0x73, 0x65, 0x5f, 0x74, 0x68, 0x65, 0x5f, 0x62, 0x65, 0x73, 0x74]

for i in range(1, 22):
	if i == 1: ctrl[i] -= 98
	if i == 2: ctrl[i] -= 82
	if i == 3: ctrl[i] -= 77
	if i == 4: ctrl[i] -= 78
	if i == 5: ctrl[i] -= 33
	if i == 6: ctrl[i] -= 94
	if i == 7: ctrl[i] -= 75
	if i == 8: ctrl[i] -= 56
	if i == 9: ctrl[i] -= 76
	if i == 10: ctrl[i] -= 106
	if i == 11: ctrl[i] -= 94
	if i == 12: ctrl[i] -= 93
	if i == 13: ctrl[i] -= 70
	if i == 14: ctrl[i] -= 90
	if i == 15: ctrl[i] -= 96
	if i == 16: ctrl[i] -= 25
	if i == 17: ctrl[i] -= 19
	if i == 18: ctrl[i] -= 22
	if i == 19: ctrl[i] -= 25
	if i == 20: ctrl[i] -= 39
	if i == 21: ctrl[i] -= 40

	ctrl[i] -= 5
	ctrl[i] = ctrl[i] ^ 0x66
	print (chr(ctrl[i]), end="")
```

Ответ: `flag{this_is_reverse!!!!!!}`
