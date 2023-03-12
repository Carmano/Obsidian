
`con = sq.connect('nameDB.db')`
`cur = con.cursor()`  - с помощью этой переменной осуществляем непосредственно работу с BD

`cur.execute (""" query """)`  - здесь пишем запросы

`result = cur.fetchall()` - результат select
`result = cur.fetchone()` - возвращает первую запись
`result - cur.fetchmany(2)` - возвращает список кортежей указаных в аргументе
