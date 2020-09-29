[❰❰❰](https://github.com/L1quide/CheatSeets/blob/master/Django_main.md)  [HOME](https://github.com/L1quide/CheatSeets/blob/master/README.md)

#### ✓ Методы модели [➦](https://django.fun/docs/django/ru/3.0/topics/db/models/#model-methods)

**__str__()** - «Волшебный метод» Python, который возвращает строковое представление любого объекта.

    class Person(models.Model):
        first_name = models.CharField(max_length=50)
        last_name = models.CharField(max_length=50)
    
        def __str__(self):
            return '%s %s' % (self.first_name, self.last_name)
            
**get_absolute_url()** - Определите метод get_absolute_url(), чтобы сообщить Django, как рассчитать канонический URL для объекта.

    def get_absolute_url(self):
        from django.urls import reverse
        return reverse('people.views.details', args=[str(self.id)])
        
     &&
     
    def get_absolute_url(self):
        return reverse('detail', args=[str(self.slug)])   
  
    <a href="{{ object.get_absolute_url }}">{{ object.name }}</a>
        
reverse( viewname , urlconf = None , args = None , kwargs = None , current_app = None ) 

##### Переопределение методов модели save() и delete().

Если надо выполнить что-то после сохранения:

    from django.db import models
    
    class Blog(models.Model):
        name = models.CharField(max_length=100)
        tagline = models.TextField()
    
        def save(self, *args, **kwargs):
            do_something()
            super().save(*args, **kwargs)  # Call the "real" save() method.
            do_something_else()
            
Как предотвратить сохранение:  

    from django.db import models
    
    class Blog(models.Model):
        name = models.CharField(max_length=100)
        tagline = models.TextField()
    
        def save(self, *args, **kwargs):
            if self.name == "Yoko Ono's blog":
                return # Yoko shall never have her own blog!
            else:
                super().save(*args, **kwargs)  # Call the "real" save() method.
                
_Важно не забывать вызывать метод суперкласса - super().save(*args, **kwargs) - чтобы гарантировать, что объект все еще сохраняется в базе данных. Если вы забудете вызвать метод суперкласса, поведение по умолчанию не произойдет, и база данных не будет затронута._


      

