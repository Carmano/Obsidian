
``` python
from collections import deque
with open(file_name) as f: 
	print(list(deque(f, 30)))
```

``` python
import os
r = os.system("tail -n 30 /path/error.log")
print(r)
```


Задача, которую я решал.
Примечание: *Текстовые файлы можно преобразовывать в тип данных список*
``` python
from sys import stdin


def main():
    fileName = stdin.readline().rstrip('\n')
    count_line = int(stdin.readline().rstrip('\n'))
    with open(fileName, 'r', encoding='utf-8') as file:
        file = list(file)
        for line in file[-count_line:]:
            print(line.strip('\n'))
  

if __name__ == '__main__':
    main()
```