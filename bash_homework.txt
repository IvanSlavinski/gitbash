::1) Посмотреть где я
slavi@LAPTOP-JRO935PT MINGW64 ~
$ pwd
/c/Users/slavi

::2) Создать папку
slavi@LAPTOP-JRO935PT MINGW64 ~
$ mkdir bash_homework

::3) Зайти в папку
slavi@LAPTOP-JRO935PT MINGW64 ~
$ cd bash_homework/

::4) Создать 3 папки
slavi@LAPTOP-JRO935PT MINGW64 ~/bash_homework
$ mkdir catalogue0 catalogue1 catalogue2

::5) Зайти в любоую папку
slavi@LAPTOP-JRO935PT MINGW64 ~/bash_homework
$ cd catalogue0

::6) Создать 5 файлов (3 txt, 2 json)
slavi@LAPTOP-JRO935PT MINGW64 ~/bash_homework/catalogue0
$ touch file1.txt file2.txt file3.txt

slavi@LAPTOP-JRO935PT MINGW64 ~/bash_homework/catalogue0
$ touch file1.json file2.json

::7) Создать 3 папки
slavi@LAPTOP-JRO935PT MINGW64 ~/bash_homework/catalogue0
$ mkdir catalogue1 catalogue2 catalogue3

::8) Вывести список содержимого папки
slavi@LAPTOP-JRO935PT MINGW64 ~/bash_homework/catalogue0
$ ls -la
total 8
drwxr-xr-x 1 slavi 197609 0 Oct 28 13:47 ./
drwxr-xr-x 1 slavi 197609 0 Oct 28 13:44 ../
drwxr-xr-x 1 slavi 197609 0 Oct 28 13:47 catalogue1/
drwxr-xr-x 1 slavi 197609 0 Oct 28 13:47 catalogue2/
drwxr-xr-x 1 slavi 197609 0 Oct 28 13:47 catalogue3/
-rw-r--r-- 1 slavi 197609 0 Oct 28 13:46 file1.json
-rw-r--r-- 1 slavi 197609 0 Oct 28 13:45 file1.txt
-rw-r--r-- 1 slavi 197609 0 Oct 28 13:46 file2.json
-rw-r--r-- 1 slavi 197609 0 Oct 28 13:45 file2.txt
-rw-r--r-- 1 slavi 197609 0 Oct 28 13:45 file3.txt

::9) + Открыть любой txt файл
slavi@LAPTOP-JRO935PT MINGW64 ~/bash_homework/catalogue0
$ nano file1.txt

::10) + написать туда что-нибудь, любой текст.
    This file contains some information that you can read.
 
::11) + сохранить и выйти.
    ^W
    ^X

slavi@LAPTOP-JRO935PT MINGW64 ~/bash_homework/catalogue0
$ cat file1.txt
This file contains some information that you can read.

::12) Выйти из папки на уровень выше
slavi@LAPTOP-JRO935PT MINGW64 ~/bash_homework/catalogue0
$ cd ..

::13) переместить любые 2 файла, которые вы создали, в любую другую папку.
slavi@LAPTOP-JRO935PT MINGW64 ~/bash_homework
$ mv catalogue0/file1.json catalogue1

slavi@LAPTOP-JRO935PT MINGW64 ~/bash_homework
$ mv catalogue0/file2.json catalogue1

::14) скопировать любые 2 файла, которые вы создали, в любую другую папку.
slavi@LAPTOP-JRO935PT MINGW64 ~/bash_homework
$ cp catalogue1/file1.json catalogue2

slavi@LAPTOP-JRO935PT MINGW64 ~/bash_homework
$ cp catalogue1/file2.json catalogue2

::15) Найти файл по имени
slavi@LAPTOP-JRO935PT MINGW64 ~/bash_homework
$ find -name file2.json
./catalogue1/file2.json
./catalogue2/file2.json

::16) просмотреть содержимое в реальном времени (команда grep) изучите как она работает.
slavi@LAPTOP-JRO935PT MINGW64 ~/bash_homework/catalogue0
$ tail -f file1.txt
This file contains some information that you can read.
This is the second line.
One more line - third.
And the fourth, to comlete all the tasks.

::17) вывести несколько первых строк из текстового файла
slavi@LAPTOP-JRO935PT MINGW64 ~/bash_homework/catalogue0
$ sed '1,2!d' file1.txt
This file contains some information that you can read.
This is the second line.

::18) вывести несколько последних строк из текстового файла
slavi@LAPTOP-JRO935PT MINGW64 ~/bash_homework/catalogue0
$ tail -n2 file1.txt
One more line - third.
And the fourth, to comlete all the tasks.

::19) просмотреть содержимое длинного файла (команда less) изучите как она работает.
slavi@LAPTOP-JRO935PT MINGW64 ~/bash_homework/catalogue0
$ less file1.txt

::20) вывести дату и время
slavi@LAPTOP-JRO935PT MINGW64 ~/bash_homework/catalogue0
$ date
Fri Oct 28 15:29:51 BST 2022


:: Задание *
:: 1) Отправить http запрос на сервер.
:: http://162.55.220.72:5006/terminal-hw-request

slavi@LAPTOP-JRO935PT MINGW64 ~/bash_homework/catalogue0
$ curl http://162.55.220.72:5006/terminal-hw-request --verbose
*   Trying 162.55.220.72:5006...
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
  0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0* Connected to 162.55.220.72 (162.55.220.72) port 5006 (#0)
> GET /terminal-hw-request HTTP/1.1
> Host: 162.55.220.72:5006
> User-Agent: curl/7.85.0
> Accept: */*
>
* Mark bundle as not supporting multiuse
* HTTP 1.0, assume close after body
< HTTP/1.0 200 OK
< Content-Type: application/json
< Content-Length: 283
< Server: Werkzeug/2.0.1 Python/3.8.10
< Date: Fri, 28 Oct 2022 12:54:30 GMT
<
{ [283 bytes data]
100   283  100   283    0     0   2733      0 --:--:-- --:--:-- --:--:--  2747{
  "Intro": "Hello!! This is your the first response from server",
  "Tasks": {
    "Task_1": "Send the next URL in terminal: http://162.55.220.72:5005/get_method?name=(set_your_String)&age=(set_your_number)",
    "result": [
      "Your_String",
      "Your_number"
    ]
  }
}

* Closing connection 0

slavi@LAPTOP-JRO935PT MINGW64 ~
$ curl http://162.55.220.72:5005/get_method?name=Ivan&age=25
[1] 891
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
  0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0
slavi@LAPTOP-JRO935PT MINGW64 ~
100    22  100    22    0     0    120      0 --:--:-- --:--:-- --:--:--   120[
  "Ivan",
  null
]

:: 2) Написать скрипт который выполнит автоматически пункты 3, 4, 5, 6, 7, 8, 13

