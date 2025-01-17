<div align="center">
  <h1> 30 Дней Python: День 12 - Модули </h1>
  <a class="header-badge" target="_blank" href="https://www.linkedin.com/in/asabeneh/">
  <img src="https://img.shields.io/badge/style--5eba00.svg?label=LinkedIn&logo=linkedin&style=social">
  </a>
  <a class="header-badge" target="_blank" href="https://twitter.com/Asabeneh">
  <img alt="Twitter Follow" src="https://img.shields.io/twitter/follow/asabeneh?style=social">
  </a>

<sub>Aвтор:
<a href="https://www.linkedin.com/in/asabeneh/" target="_blank">Asabeneh Yetayeh</a><br>
<small> Второе издание: Июль, 2021</small>
</sub>

</div>
</div>

[<< День 11](../11_Day_Functions/11_functions.md) | [День 13>>](../13_Day_List_comprehension/13_list_comprehension.md)

![30DaysOfPython](../images/30daysofpython.png)

- [📘 Day 12](#-day-12)
  - [Модули](#модули)
    - [Что такое модуль](#что-такое-модуль)
    - [Создание модуля](#создание-модуля)
    - [Импортирование модуля](#импортирование-модуля)
    - [Импорт функций из модуля](#импорт-функций-из-модуля)
    - [Импорт функций из модуля с переименованием](#импорт-функций-из-модуля-с-переименованием)
  - [Импорт встроенных модулей](#импорт-встроенных-модулей)
    - [Модуль OS](#модуль-os)
    - [Модуль Sys](#модуль-sys)
    - [Модуль Statistics](#модуль-statistics)
    - [Модуль Math](#модуль-math)
    - [Модуль String](#модуль-string)
    - [Модуль Random](#модуль-random)
  - [💻 Упржнения: День 12](#-упржнения-день-12)
    - [Упржнения: Уровень 1](#упржнения-уровень-1)
    - [Упржнения: Уровень 2](#упржнения-уровень-2)
    - [Упржнения: Уровень 3](#упржнения-уровень-3)

# 📘 Day 12

## Модули

### Что такое модуль

Модуль - это файл, содержащий набор кодов или функций, которые могут быть задействованы в вашем коде. Модуль может быть файлом, содержащим одну переменную, функцию или большой набор строк кода.

### Создание модуля

Для создания модуля мы пишем наш код на языке Python и сохраняем его с расширением **.py**. Давайте создаим файл с именем mymodule.py внутри папки вашего проекта и напишем в нем код.

```py
# файл mymodule.py 
def generate_full_name(firstname, lastname):
    return firstname + ' ' + lastname
```

А теперь создами файл main.py в вашей папке нашего проекта и импортируем модуль mymodule.py.

### Импортирование модуля

Чтобы импортировать файл мы используем _import_ и название файла.

```py
# файл main.py
import mymodule
print(mymodule.generate_full_name('Питер', 'Паркер')) # Питер Паркер
```

### Импорт функций из модуля

Мы можем отдель импортировать функцию, которая нам нужна.

```py
# файл main.py 
from mymodule import generate_full_name, sum_two_nums, person, gravity
print(generate_full_name('Питер', 'Паркер'))
print(sum_two_nums(1,9))
mass = 100;
weight = mass * gravity
print(weight)
print(person['firstname'])
```

### Импорт функций из модуля с переименованием

При импорте мы можем переименовать имя модуля.

```py
# файл main.py 
from mymodule import generate_full_name as fullname, sum_two_nums as total, person as p, gravity as g
print(fullname('Питер','Паркер'))
print(total(1, 9))
mass = 100;
weight = mass * g
print(weight)
print(p)
print(p['firstname'])
```

## Импорт встроенных модулей

Like other programming languages we can also import modules by importing the file/function using the key word _import_. Let's import the common module we will use most of the time. Some of the common built-in modules: _math_, _datetime_, _os_,_sys_, _random_, _statistics_, _collections_, _json_,_re_

### Модуль OS

Как и в других языках программирования, в Python есть встроенные модули, которые мы можем импортировать, используя *import*. Давайте попробуем импортировать самые часто используемые модули. К таким модулям относятся: math, datetime, os, sys, random, statistics, collections, json, re.

```py
# импорт модуля
import os
# создание директории
os.mkdir('directory_name')
# изменение текущей директории
os.chdir('path')
# получение текущей рабочей директории
os.getcwd()
# удаление директории
os.rmdir()
```

### Модуль Sys

Модуль sys в Python предоставляет функции и переменные, связанные с системой и интерпретатором Python. Он позволяет взаимодействовать с различными компонентами операционной системы, получать информацию о среде выполнения Python, а также управлять выполнением программы. Например, функция sys.argv возвращает список аргументов командной строки, переданных в скрипт Python. Элемент с индексом 0 в списке всегда содержит имя скрипта.

Пример файла script.py::

```py
import sys
#print(sys.argv[0], sys.argv[1], sys.argv[2])   # эта строка выведет: имя_файла аргумент1 аргумент2
print('Welcome {}. Enjoy  {} challenge!'.format(sys.argv[1], sys.argv[2]))
```

А теперь, давайте проверим работоспособность этого скрипта:

```sh
python script.py Asabeneh 30DaysOfPython
```

Результатом будет:

```sh
Welcome Asabeneh. Enjoy  30DayOfPython challenge! 
```

Рассотрим ещё немного полезных команд модуля sys:

```py
# для выхода из программы
sys.exit()
# Получение максимального значения целочисленной переменной
sys.maxsize
# Получение пути 
sys.path
# Получение версии Python, которую мы используем sys.version
```

### Модуль Statistics

В модуле Statistics определены популярные статистические функции, такие как *mean*, *median*, *mode*, *stdev* и т. д.

```py
from statistics import * # импортируем все функции из модуля statistics
ages = [20, 20, 4, 24, 25, 22, 26, 20, 23, 22, 26]
print(mean(ages))       # ~22.9
print(median(ages))     # 23
print(mode(ages))       # 20
print(stdev(ages))      # ~2.3
```

### Модуль Math


Модуль math содержит множество математических операций и констант.
```py
import math
print(math.pi)           # 3.141592653589793, число пи
print(math.sqrt(2))      # 1.4142135623730951, вычисление квадратного корня
print(math.pow(2, 3))    # 8.0, возведение в степень
print(math.floor(9.81))  # 9, округление до ближайшего меньшего целого
print(math.ceil(9.81))   # 10, округление до ближайшего большего целого
print(math.log10(100))   # 2, десятичный логарифм
```

Сейчас мы импортировали модуль math, который содержит множество функций. Чтобы проверить, какие именно функции есть в модуле, мы можем использовать функцию help(math) или dir(math). Это позволит нам увидеть доступные функции в модуле. Если мы хотим импортировать только определенную функцию из модуля, мы импортируем ее следующим образом:

```py
from math import pi
print(pi)
```

А ещё, мы можем импортировать сразу несколько функций:

```py

from math import pi, sqrt, pow, floor, ceil, log10
print(pi)                 # 3.141592653589793
print(sqrt(2))            # 1.4142135623730951
print(pow(2, 3))          # 8.0
print(floor(9.81))        # 9
print(ceil(9.81))         # 10
print(math.log10(100))    # 2

```

Однако, если мы хотим импортировать все функции из модуля math, мы можем использовать символ  \*.

```py
from math import *
print(pi)                  # 3.141592653589793, число пи
print(sqrt(2))             # 1.4142135623730951, квадратный корень
print(pow(2, 3))           # 8.0, возведение в степень
print(floor(9.81))         # 9, округление вниз до целого цисла
print(ceil(9.81))          # 10, округление вверх до целого цисла
print(math.log10(100))     # 2
```

При импорте мы также можем изменить имя функции:

```py
from math import pi as  PI
print(PI) # 3.141592653589793
```

### Модуль String

Модуль *string* представляет собой полезный модуль для множества задач. Приведенный ниже пример демонстрирует некоторые возможности модуля *string*.

```py
import string
print(string.ascii_letters) # abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ
print(string.digits)        # 0123456789
print(string.punctuation)   # !"#$%&'()*+,-./:;<=>?@[\]^_`{|}~
```

### Модуль Random

А теперь давайте импортируем модуль _random_ и посмотрим как работает он! Функция random() возвращает нам значение между 0 и 0.9999.... Модуль random имеет много функций, но в этом разделе мы будем использовать только random и randint.

```py
from random import random, randint
print(random())  # функция random не принимает аргументов; она возвращает значение между 0 и 0.9999
print(randint(5, 20))  # функция randint возвращает случайное целое число в диапазоне [5, 20] включительно
```

🌕 Ты уверенно движешься вперед! Так держать! Ты только что завершил 12 день челленджа и стал на 12 шагов ближе к мечте. Закрепи свой результат практическими заданиями.

## 💻 Упржнения: День 12

### Упржнения: Уровень 1

1. Напишите функцию, которая генерирует случайный идентификатор пользователя длинной в 6 символов(random_user_id).
   ```py
     print(random_user_id());
     '1ee33d'
   ```
2. Модифицируйте прошлую задачу. Объявите функцию с именем user_id_gen_by_user. Она не принимает никаких параметров, но запрашивает два ввода с помощью функции input(). Первый - количество символов, второй - количество идентификаторов, которые должны быть сгенерированы.
   
```py
print(user_id_gen_by_user()) # user input: 5 5
#output:
#kcsy2
#SMFYb
#bWmeq
#ZXOYh
#2Rgxf
   
print(user_id_gen_by_user()) # 16 5
#1GCSgPLMaBAVQZ26
#YD7eFwNQKNs7qXaT
#ycArC5yrRupyG00S
#UbGxOFI7UXSWAyKN
#dIV0SSUTgAdKwStr
```

3. Напишите функцию rgb_color_gen. Она будет генерировать цвета RGB (3 значения от 0 до 255 каждое).
   
```py
print(rgb_color_gen())
# rgb(125,244,255) - вывод должен быть такого формата
```

### Упржнения: Уровень 2

1. Напишите функцию list_of_hexa_colors которая возвращает любое количество последовательностей содержащих шестнадцатеричный цвет (цвета должны быть записаны после #). Шестнадцатеричная система состоит из 6 символов: чисел 0-9 и первых 6 букв английского алфавита a-f.
2. Напишите функцию list_of_rgb_colors, которая возвращает любое количество цветов RGB.
3. Напишите функцию generate_colors, которая может генерировать любое количество шестнадцатеричных или RGB цветов.

```py
   generate_colors('hexa', 3) # ['#a3e12f','#03ed55','#eb3d2b'] 
   generate_colors('hexa', 1) # ['#b334ef']
   generate_colors('rgb', 3)  # ['rgb(5, 55, 175','rgb(50, 105, 100','rgb(15, 26, 80'] 
   generate_colors('rgb', 1)  # ['rgb(33,79, 176)']
   ```

### Упржнения: Уровень 3

1. Создайте функцию shuffle_list, которая принимает список в качестве параметра и возвращает перемешанный список.
2. Напишите функцию, которая возвращает последовательность из семи случайных чисел в диапазоне от 0 до 9. Все числа должны быть уникальными.

🎉 ПОЗДРАВЛЯЕМ ! 🎉

[<< День 11](../11_Day_Functions/11_functions.md) | [День 13>>](../13_Day_List_comprehension/13_list_comprehension.md)
