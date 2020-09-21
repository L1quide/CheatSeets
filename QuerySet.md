[❰❰❰](https://github.com/L1quide/CheatSeets/blob/master/Django_main.md)  [HOME](https://github.com/L1quide/CheatSeets/blob/master/README.md)

#### ✓ Работа с запросами [➦](https://django.fun/docs/django/ru/3.0/topics/db/queries/)

##### Создание объектов save()

    b = Blog(name='Beatles Blog', tagline='All the latest Beatles news.')
    b.save()
    
##### Сохранение изменений в объектах

    b5.name = 'New name'
    b5.save()

##### create()

Удобный метод для создания объекта и сохранения всего за один шаг.

    p = Person.objects.create(first_name="Bruce", last_name="Springsteen")

##### Сохранение полей ForeignKey и ManyToManyField

    from blog.models import Blog, Entry
    entry = Entry.objects.get(pk=1)
    cheese_blog = Blog.objects.get(name="Cheddar Talk")
    entry.blog = cheese_blog
    entry.save()
    
##### Обновление ManyToManyField

    from blog.models import Author
    joe = Author.objects.create(name="Joe")
    entry.authors.add(joe)  
    
_Чтобы добавить несколько записей в ManyToManyField за один раз, включите в вызов несколько аргументов add()_

    john = Author.objects.create(name="John")
    paul = Author.objects.create(name="Paul")
    george = Author.objects.create(name="George")
    ringo = Author.objects.create(name="Ringo")
    entry.authors.add(john, paul, george, ringo)
    
    
##### Получение объектов

###### ▪ Получение всех объектов all()

    all_entries = Entry.objects.all()
    
###### ▪ Получение одного объекта с помощью get()

    one_entry = Entry.objects.get(pk=1)
    
##### Ограничение QuerySet 

Вернуть первые 5 объектов (LIMIT 5):

    Entry.objects.all()[:5]

Вернуть объекты с шестого по десятый (OFFSET 5 LIMIT 5):

    Entry.objects.all()[5:10]

Вернуть список каждого второго объекта из первых 10:

    Entry.objects.all()[:10:2]

_Отрицательное индексирование (т.е. Entry.objects.all()[-1]) не поддерживается._