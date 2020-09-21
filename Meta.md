[❰❰❰](https://github.com/L1quide/CheatSeets/blob/master/Django_main.md)  [HOME](https://github.com/L1quide/CheatSeets/blob/master/README.md)

#### Опции Meta

Метаданные модели - это «все, что не является полем», например параметры сортировки (ordering), имя таблицы базы данных (db_table) или удобочитаемые имена в единственном и множественном числе (verbose_name и verbose_name_plural). Это все не обязательные параметры, и добавление class Meta к модели совершенно необязательно.


    from django.db import models
    
    class Ox(models.Model):
        horn_length = models.IntegerField()
    
        class Meta:
            ordering = ["horn_length"]
            verbose_name_plural = "oxen"
            
[Полный список всех возможных опций Meta](https://django.fun/docs/django/ru/3.0/ref/models/options/)