[❰❰❰](https://github.com/L1quide/CheatSeets/blob/master/Django_main.md)  [HOME](https://github.com/L1quide/CheatSeets/blob/master/README.md)

#### Опции Meta

Метаданные модели - это «все, что не является полем», например параметры сортировки (ordering), имя таблицы базы данных (db_table) или удобочитаемые имена в единственном и множественном числе (verbose_name и verbose_name_plural). Это все не обязательные параметры, и добавление class Meta к модели совершенно необязательно.


    from django.db import models
    
    class Ox(models.Model):
        horn_length = models.IntegerField()
    
        class Meta:
            ordering = ["horn_length"]
            verbose_name_plural = "oxen"
            
            
**ordering** - Это кортеж или список строк и/или выражений запроса. Каждая строка представляет собой имя поля с необязательным префиксом «-», который указывает в порядке убывания. Поля без начального «-» будут упорядочены по возрастанию. Используйте знак «?» для случайной сортировки.

Например, чтобы упорядочить по возрастанию поля pub_date, используйте это:

    ordering = ['pub_date']   
    
Чтобы упорядочить по убыванию pub_date, используйте это:

    ordering = ['-pub_date']
    
Чтобы упорядочить по pub_date по убыванию, затем по author по возрастанию, используйте это:

    ordering = ['-pub_date', 'author']
    
Вы также можете использовать выражения запросов. Чтобы упорядочить по author по возрастанию и сделать сортировку значений NULL последней, используйте это:

    from django.db.models import F
    
    ordering = [F('author').asc(nulls_last=True)]
    
    
**indexes** - Список индексов, который вы хотите определить в модели

    class Customer(models.Model):
        first_name = models.CharField(max_length=100)
        last_name = models.CharField(max_length=100)
    
        class Meta:
            indexes = [
                models.Index(fields=['last_name', 'first_name']),
                models.Index(fields=['first_name'], name='first_name_idx'),
            ]
       
**verbose_name** - Удобочитаемое имя для объекта, единственное число

    verbose_name = "pizza"
    
**verbose_name_plural** - Имя во множественном числе для объекта

    verbose_name_plural = "stories"



           
[Полный список всех возможных опций Meta](https://django.fun/docs/django/ru/3.0/ref/models/options/)