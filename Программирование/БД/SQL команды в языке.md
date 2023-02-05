
CREATE DATABASE NAMEDATABASE - Создание базы данных


DROP DATABASE NAMEDATABASE - Удаление БД


CREATE TABLE _NAMETABLE_ (title text, full_text text, views integer, avtor text) - Создание таблицы и указания ее полей. title, full_text, avtor - это поля типа text и views типа integer 


DROP TABLE NAMETABLE - удаление таблицы


INSERT INTO _NAMETABLE_ VALUES (заполняем значения) - добавляет запись в таблицу 


SELECT * FROM NAMETABLE - Выборка таблицы NAMETABLE


DELETE FROM NAMETABLE  - Удаляет все записи из этой таблицы


DELETE FROM NAMETABLE WHERE rowid = 2 - удаляет записи у которых rowid = 2 


UPDATE NAMETABLE SET TABLEFIELD = "SOMETHING TO NEED"
