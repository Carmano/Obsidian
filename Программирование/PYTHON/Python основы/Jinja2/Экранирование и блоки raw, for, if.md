
## raw

![[Pasted image 20221129225552.png]]
*пример 1*
С помощью {%raw%} *текст* {%endraw%} Можно вывести на экран текст такой какой он есть, без измененния {{  }}
![[Pasted image 20221129225720.png]]
*результат примера 1*


## экранирование 
![[Pasted image 20221129233609.png]]
*пример 2*
Иногда на html странице надо вывести текст такой какой он есть, допустим пишим мы ![[Pasted image 20221129233822.png]] , а на экран выводится ![[Pasted image 20221129233855.png]]
чтобы этого избежать применяют экранирование написанное пример номер 2, это фигня используется весьма часто поэтому придумали метод escape 

![[Pasted image 20221129234021.png]]
*пример 3*

Пример номер 3 делает, тоже самое, что и пример 2, но написан через метод escape это удобне и приятнее
*Примечание надо импортировать*


## блок for
![[Pasted image 20221130001053.png]]
*пример 4* 

{% for c in cities %}  ##переменная тут cities, а не c, с - это локальная переменная созданная для итерации
так же надо заканчивать цикла {% endfor %}
![[Pasted image 20221130001351.png]]
*результат номера 4*

в пример есть перенос строки, он исходит от строки, где находится for если хотим его убрать то надо написать перед конечным процентом '-', так же его можно писать после первого процента ![[Pasted image 20221130002153.png]]
так же можно писать и в endfor 


## if else elif

![[Pasted image 20221130002416.png]]

вроде работает так же как for 