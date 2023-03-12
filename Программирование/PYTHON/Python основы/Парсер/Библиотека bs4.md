
BeautifulSoup является библиотекой Python для парсинга HTML и XML документов. Часто используется для **скрапинга веб-страниц**. BeautifulSoup позволяет трансформировать сложный HTML-документ в сложное древо различных объектов Python. Это могут быть теги, навигация или комментарии.


### Просто код
``` python
from bs4 import BeautifulSoup


with open("index.html", "r") as f:
    contents = f.read()
    soup = BeautifulSoup(contents, 'lxml')

    print(soup.h2)
    print(soup.head)
    print(soup.li)

```

### recursiveChildGenerator()

Метод позволяет пробежаться по содрежимому HTML (генератор)

### children

При помощи атрибута `children` можно вывести все дочерние теги. Возвращает итератор

``` python
from bs4 import BeautifulSoup

with open("index.html", "r") as f:
    contents = f.read()
    soup = BeautifulSoup(contents, 'lxml')
    root = soup.html # определяем родительский тег
    root_childs = [e.name for e in root.children if e.name is not None]
    print(root_childs)
```
Выводит дочерние теги, тега html 


### descendants

тоже самое, что и children, но возвращает все дочерние элементы родительского элемента


### prettify()

html - текст выглядит аккуратне


Одна из распространенных задач — извлечь все URL-адреса, найденные на странице в тегах a:

``` python
for link in soup.find_all('a'):
    print(link.get('href'))
```

Другая распространенная задача — извлечь весь текст со страницы:

`print(soup.get_text())`


https://python-scripts.com/beautifulsoup-html-parsing