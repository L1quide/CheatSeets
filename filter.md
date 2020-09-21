[❰❰❰](https://github.com/L1quide/CheatSeets/blob/master/Django_main.md)  [HOME](https://github.com/L1quide/CheatSeets/blob/master/README.md)

#### ✓ Поиск по полям [➦](https://django.fun/docs/django/ru/3.0/topics/db/queries/#field-lookups)

###### ▪ filter(**kwargs) & exclude(**kwargs)
    
**filter** - Возвращает новый QuerySet, содержащий объекты, которые соответствуют заданным параметрам поиска.

**exclude** - Возвращает новый QuerySet, содержащий объекты, которые не соответствуют указанным параметрам поиска.

▪ Фильтры можно объединять в цепочки

    Entry.objects.filter(headline__startswith='What')
    .exclude(pub_date__gte=datetime.date.today())
    .filter(pub_date__gte=datetime.date(2005, 1, 30))

▪ Отфильтрованные QuerySet являются уникальными

    q1 = Entry.objects.filter(headline__startswith="What")
    q2 = q1.exclude(pub_date__gte=datetime.date.today())
    q3 = q1.filter(pub_date__gte=datetime.date.today())
    
    
_Поиск по полю - это то, как вы определяете содержание выражения SQL WHERE. 
Они указываются в качестве аргументов ключевых слов для методов filter(), exclude() и get() класса QuerySet._

▪ Базовые аргументы поиска по ключевым словам имеют вид field__lookuptype=value.
  
    Entry.objects.filter(pub_date__lte='2006-01-01')
    
    SELECT * FROM blog_entry WHERE pub_date <= '2006-01-01';
    
▪ Поле, указанное в поиске, должно быть именем поля модели.

▪ ForeignKey - можно указать имя поля с суффиксом _id.

    Entry.objects.filter(blog_id=4)
    
###### ▪ «Точное» совпадение exact

    Entry.objects.get(headline__exact="Cat bites dog")
    
    SELECT ... WHERE headline = 'Cat bites dog';
    
###### ▪ Соответствие без учета регистра iexact

    Blog.objects.get(name__iexact="beatles blog")
    
###### ▪ Проверка содержимого в зависимости от регистра contains & icontains.

    Entry.objects.get(headline__contains='Lennon')
    
    SELECT ... WHERE headline LIKE '%Lennon%';
    
###### ▪ «Начинается с» и «заканчивается» соответственно startswith, endswith & istartswith, iendswith


#### ✓ Поиск, который использует отношения

