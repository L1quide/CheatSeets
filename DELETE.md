[❰❰❰](https://github.com/L1quide/CheatSeets/blob/master/PostgreSQL.md) [HOME](https://github.com/L1quide/CheatSeets/blob/master/README.md)

#### DELETE

DELETE — удалить записи таблицы

###### Синтаксис

    [ WITH [ RECURSIVE ] запрос_WITH [, ...] ]
    DELETE FROM [ ONLY ] имя_таблицы [ * ] [ [ AS ] псевдоним ]
        [ USING список_USING ]
        [ WHERE условие | WHERE CURRENT OF имя_курсора ]
        [ RETURNING * | выражение_результата [ [ AS ] имя_результата ] [, ...] ]