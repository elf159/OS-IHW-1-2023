# OS-IHW-1-2023
Карпов Михаил Дмитриевич (БПИ_212)

Задание сделано на критерии для 7 баллов (а также 4,5 и 6).

Вариант 6: Разработать программу, заменяющую все согласные буквы в заданной ASCII-строке их ASCII кодами в десятичной системе счисления.

# Компиляция:
```
clang mark4.c -o mark4
...
clang mark7.c -o mark7
```

# Формат входных данных:
Через параметры входной строки передаются параметры:
```
{путь к исполняемому файлу} {входной файл} {выходной файл}
```
Пример:
```
./mark4 input.txt output.txt
```
Пример входного и выходного файла:
```
test.txt: abcdef

answer.txt: a9899100e102
```
Тестовое покрытие общее для всех оценок - в папке tests.
# 4 балла
В файле mark4.c находится решение задачи, используются неименованные каналы, 3 дочерних процесса

Схема работы программы:

<img width="1054" alt="mark4" src="https://user-images.githubusercontent.com/89385262/226207484-0e701f8e-d9fe-439d-a6d3-e849dfa40303.png">


Родительский процесс вызывает поочередно 3 дочерних процесса:

Для работы с файлами используются функции read и write.

Первый процесс считывает данные из входного файла и по неименованному каналу fd1 передает их второму процессу.

Второй процесс выполняет обработку данных и по неименованному каналу fd2 передает данные третьему процессу.

Третий процесс выполняет вывод результата работы программы в выходной файл.

Буфер имеет размер в 5000 байт.

# 5 баллов
В файле mark5.c находится решение задачи, используются именованные каналы, 3 дочерних процесса

Схема работы программы:

<img width="1037" alt="mark5" src="https://user-images.githubusercontent.com/89385262/226207479-cc7985bd-d83d-479e-b082-5efd837db73e.png">

Родительский процесс вызывает поочередно 3 дочерних процесса:

Для работы с файлами используются функции read и write.

Первый процесс считывает данные из входного файла и по именованному каналу 'my_pipe1' передает их второму процессу.

Второй процесс выполняет обработку данных и по именованному каналу 'my_pipe2' передает данные третьему процессу.

Третий процесс выполняет вывод результата работы программы в выходной файл.

Буфер имеет размер в 5000 байт.

# 6 баллов
В файле mark6.c находится решение задачи, используются неименованные каналы, 2 дочерних процесса

Схема работы программы:

<img width="848" alt="mark6" src="https://user-images.githubusercontent.com/89385262/226207476-afc0893c-a87b-40b3-ac6f-a2b7faa1fb6a.png">


Родительский процесс вызывает поочередно 2 дочерних процесса:

Для работы с файлами используются функции read и write.

Первый процесс считывает данные из входного файла и по неименованному каналу fd1 передает их второму процессу.

Второй процесс выполняет обработку данных и по неименованному каналу fd2 передает данные обратно первому процессу.

Первый процесс выполняет вывод результата работы программы в выходной файл.

Буфер имеет размер в 5000 байт.

# 7 баллов
В файле mark7.c находится решение задачи, используются именованные каналы, 2 дочерних процесса

Схема работы программы:

<img width="883" alt="mark7" src="https://user-images.githubusercontent.com/89385262/226207367-d7e75e87-eeae-4722-816f-862750c4b96f.png">

Родительский процесс вызывает поочередно 2 дочерних процесса:

Для работы с файлами используются функции read и write.

Первый процесс считывает данные из входного файла и по именованному каналу 'my_pipe1' передает их второму процессу.

Второй процесс выполняет обработку данных и по именованному каналу 'my_pipe2' передает данные обратно первому процессу.

Первый процесс выполняет вывод результата работы программы в выходной файл.

Буфер имеет размер в 5000 байт.
