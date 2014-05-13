Javascript-библиотека для определения пола по фамилии, имени, отчеству на русском языке
=======================================================================================

JavaScript код, который по традиционным русским Имени, Фамилии и Отчеству определяет пол.

### Установка
Подключите к вашему приложению скрипт, например:

`<script src="Sex.js"></script>`

### Инициализация
`new Sex("Иванов", "Иван", "Иванович")`

Например:

`var sex = new Sex("Иванов", "Иван", "Иванович");`

### Получение результата

`new Sex("Иванов", "Иван", "Иванович").get_gender`

Например:

`var sex = new Sex("Иванов", "Иван", "Иванович");
 sex.get_gender;`

### Формат ввода

Аргументы вводятся в виде строк (string):

* Первый аргумент: фамилия.
* Второй аргумент: имя.
* Третий аргумент: отчество.

Если нет одной из частей имени, то необходимо передать пустую строку (""). Например:

`var sex = new Sex("Иванов", "", "");`


### Формат вывода

Метод *.get_gender* возвращает один из трех вариантов:

* *1* (мужской пол),
* *0* (женский пол),
* *undefined* (не удалось определить пол).


Как это работает
----------------

Скрипт пытается определить пол сначала у каждой строки отдельно:

* по фамилии,
* по имени,
* по отчеству.

Если в одной или в нескольких строках удалось определить один пол и не определился другой, то этот пол возвращается как определенный.

Скрипт возвращает undefined, если:

* не удалось определить пол ни по одной из строк,
* в разных строках был определен разный пол.


### Определение пола по фамилии

По фамилии пол определяется по окончанию.

В переменной *Sex.surname_completions* содержится два массива, в которых перечислены наиболее распространенные окончания традиционных русских фамилий.


### Определение пола по отчеству

По отчеству пол определяется по окончанию, так же как в определении по фамилии.

В переменной *Sex.surname_completions* содержится два массива, в которых перечислены наиболее распространенные окончания традиционных русских отчеств.

Кстати, определение по отчеству наиболее эффективно и покрывает наибольший процент возможных вариантов. Тем ни менее наш скрипт пытается определить пол по всем трем частям имени, потому что часто бывают случаи, когда есть только одна или две части имени.


### Определение пола по имени

Пол по имени определяется просто по соответствию наиболее распространенным русским именам.

Список имен находится в переменной *Sex.names*.



Лицензия
--------

sexing_by_russian_name является бесплатным ПО, подробности в файле LICENSE.


Благодарность
-------------

Скрипт написан в студии «[Цифрономика](http://cifronomika.ru/)». Авторы:
* [Вадим Галкин](https://github.com/vadimiztveri/)
* [Александр Борисов](https://github.com/aishek)
* [Кирилл Храпков](https://github.com/cubbiu)
