## Создание своего первого графического интерфейса

![[Pasted image 20221224205509.png]]

``` python
from tkinter import *  
  
  
def main():  
    window = Tk()  
    window.title('Добро пожаловать в приложение')  
    window.mainloop()  
  
  
if __name__ == '__main__':  
    main()
```

Прекрасно! Наше приложение работает.  
Последняя строка вызывает функцию `mainloop`. Эта функция вызывает бесконечный цикл окна, поэтому окно будет ждать любого взаимодействия с пользователем, пока не будет закрыто.

В случае, если вы забудете вызвать функцию `mainloop` , для пользователя ничего не отобразится.

## Создание виджета Label

Чтобы добавить текст в наш предыдущий пример, мы создадим `lbl` , с помощью класса `Label`, например:

```python
lbl = Label(window, text="Привет")
```

Затем мы установим позицию в окне с помощью функции `grid` и укажем ее следующим образом:

```python
lbl.grid(column=0, row=0)
```

Полный код, будет выглядеть следующим образом:

```python
from tkinter import *  
  
  
window = Tk()  
window.title("Добро пожаловать в приложение PythonRu")  
lbl = Label(window, text="Привет") 
lbl.grid(column=0, row=0)  
window.mainloop()
```

И вот как будет выглядеть результат:  
![Обучение Python GUI (уроки по Tkinter)](https://pythonru.com/wp-content/uploads/2019/01/uroki-po-tkinter-2.png)
Если функция `grid` не будет вызвана, текст не будет отображаться.


window.geometry('400x250') - устновить размер окна


## Добавление виджета Button

Начнем с добавления кнопки в окно. Кнопка создается и добавляется в окно так же, как и метка:

```python
btn = Button(window, text="Не нажимать!")
btn.grid(column=1, row=0)
```

Наш код будет выглядеть вот так:

```python
from tkinter import *  
  

window = Tk()  
window.title("Добро пожаловать в приложение PythonRu")  
window.geometry('400x250')  
lbl = Label(window, text="Привет", font=("Arial Bold", 50))  
lbl.grid(column=0, row=0)  
btn = Button(window, text="Не нажимать!")  
btn.grid(column=1, row=0)  
window.mainloop()
```

Результат будет следующим:  
![Обучение Python GUI (уроки по Tkinter)](https://pythonru.com/wp-content/uploads/2019/01/uroki-po-tkinter-4.png)
Обратите внимание, что мы помещаем кнопку во второй столбец окна, что равно 1. Если вы забудете и поместите кнопку в том же столбце, который равен 0, он покажет только кнопку.

Вы можете поменять цвет текста кнопки или любого другого виджета, используя свойство `fg`.  
Кроме того, вы можете поменять цвет фона любого виджета, используя свойство `bg`.

```python
btn = Button(window, text="Не нажимать!", bg="black", fg="red")
```

![Обучение Python GUI (уроки по Tkinter)](https://pythonru.com/wp-content/uploads/2019/01/uroki-po-tkinter-5.png)
Теперь, если вы попытаетесь щелкнуть по кнопке, ничего не произойдет, потому что событие нажатия кнопки еще не написан


