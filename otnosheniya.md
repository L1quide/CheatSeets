[❰❰❰](https://github.com/L1quide/CheatSeets/blob/master/Django_main.md)  [HOME](https://github.com/L1quide/CheatSeets/blob/master/README.md)



##### Отношения много-к-одному [➦](https://django.fun/docs/django/ru/3.0/topics/db/examples/many_to_one/)

**ForeignKey** требует позиционный аргумент: класс, к которому относится модель.

    from django.db import models
    
    class Manufacturer(models.Model):
        # ...
        pass
    
    class Car(models.Model):
        manufacturer = models.ForeignKey(Manufacturer, on_delete=models.CASCADE)
        # ...

##### Отношения многие ко многим [➦](https://django.fun/docs/django/ru/3.0/topics/db/examples/many_to_many/)

**ManyToManyField** требует позиционный аргумент: класс, к которому относится модель.

Неважно, какая модель имеет ManyToManyField, но вы должны поместить ее только в одну из моделей, а не в обе. Как правило, экземпляры ManyToManyField должны помещаться в объект, который будет редактироваться в форме.

    from django.db import models
    
    class Topping(models.Model):
        # ...
        pass
    
    class Pizza(models.Model):
        # ...
        toppings = models.ManyToManyField(Topping)
        
Поля ManyToManyField также принимают ряд дополнительных [аргументов](https://django.fun/docs/django/ru/3.0/ref/models/fields/#manytomany-arguments)

##### Дополнительные поля в отношениях «многие ко многим» [➦](https://django.fun/docs/django/ru/3.0/topics/db/models/#extra-fields-on-many-to-many-relationships)

    from django.db import models
    
    class Person(models.Model):
        name = models.CharField(max_length=128)
    
        def __str__(self):
            return self.name
    
    class Group(models.Model):
        name = models.CharField(max_length=128)
        members = models.ManyToManyField(Person, through='Membership')
    
        def __str__(self):
            return self.name
    
    class Membership(models.Model):
        person = models.ForeignKey(Person, on_delete=models.CASCADE)
        group = models.ForeignKey(Group, on_delete=models.CASCADE)
        date_joined = models.DateField()
        invite_reason = models.CharField(max_length=64)


##### Отношения один-к-одному [➦](https://django.fun/docs/django/ru/3.0/topics/db/examples/one_to_one/)






