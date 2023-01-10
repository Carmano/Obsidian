### Что такое JSON в Python?
JSON в Python обозначает JavaScript Object Notation, который является широко используемым форматом данных для обмена данными в Интернете. JSON – идеальный формат для организации передачи данных между клиентом и сервером. Его синтаксис аналогичен языку программирования JavaScript.

Основная цель JSON – передавать данные между клиентом и веб-сервером. Это простой в освоении и наиболее эффективный способ обмена данными. Его можно использовать с различными языками программирования, такими как Python, Perl, Java и т. д.

JSON в основном поддерживает 6 типов данных в JavaScript:

- String;
- Number;
- Boolean;
- Null;
- Object;
- Array.


### JSON построен на двух структурах:
- Он хранит данные в парах имя / значение. Он рассматривается как объект, запись, словарь, хеш-таблица, список с ключами.
- Упорядоченный список значений рассматривается как массив, вектор, список или последовательность.

Кодирование данных JSON называется сериализацией. Сериализация – это метод, при котором данные преобразуются в последовательности байтов и передаются по сети. Десериализация – это процесс, обратный декодированию данных, преобразованных в формат JSON. Этот модуль включает в себя множество встроенных функций.
![[Pasted image 20230107180205.png]]

![[Pasted image 20230107180219.png]]
### Функция dump()

``` python
Import json 
# Key:value mapping 
student  = { 
"Name" : "Peter", 
"Roll_no" : "0090014", 
"Grade" : "A", 
"Age": 20, 
    "Subject": ["Computer Graphics", "Discrete Mathematics", "Data Structure"] 
} 
 
with open("data.json","w") as write_file: 
    json.dump(student,write_file) 
```


### Функция dumps()

``` python
import json 
# Key:value mapping 
student  = { 
"Name" : "Peter", 
"Roll_no" : "0090014", 
"Grade" : "A", 
"Age": 20 
} 
b = json.dumps(student) 
 
print(b) 

```


### Функция load()

``` python 
import json 
# Key:value mapping 
student  = { 
"Name" : "Peter", 
"Roll_no" : "0090014", 
"Grade" : "A", 
"Age": 20, 
} 
 
with open("data.json","w") as write_file: 
    json.dump(student,write_file) 
 
with open("data.json", "r") as read_file: 
    b = json.load(read_file) 
print(b) 

```