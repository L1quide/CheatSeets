[❰❰❰](https://github.com/L1quide/CheatSeets/blob/master/Django_main.md)  [HOME](https://github.com/L1quide/CheatSeets/blob/master/README.md)

#### ✓ django-admin и manage.py [➦](https://django.fun/docs/django/ru/3.1/ref/django-admin/)

[django-admin startproject name [directory]](https://django.fun/docs/django/ru/3.1/ref/django-admin/#django-admin-startproject) - Создает структуру каталогов проекта Django для данного имени проекта в текущем каталоге или в указанном месте назначения.

[django-admin startapp name [directory]](https://django.fun/docs/django/ru/3.1/ref/django-admin/#startapp) - Создает структуру каталогов приложения Django для данного имени приложения в текущем каталоге или в указанном месте назначения.

[django-admin createsuperuser](https://django.fun/docs/django/ru/3.1/ref/django-admin/#django-admin-createsuperuser) - Создает учетную запись суперпользователя (пользователя со всеми правами). 

[django-admin changepassword [<username>]](https://django.fun/docs/django/ru/3.1/ref/django-admin/#changepassword) - Позволяет изменить пароль пользователя.

[django-admin runserver [addrport]](https://django.fun/docs/django/ru/3.1/ref/django-admin/#runserver) - Запускает облегченный веб-сервер разработки на локальном компьютере. 

[django-admin sendtestemail [email [email ...]]](https://django.fun/docs/django/ru/3.1/ref/django-admin/#sendtestemail) - Отправляет тестовое электронное письмо (чтобы подтвердить, что отправка электронной почты через Django работает) указанному получателю (ям).

###### Миграции [➦](https://django.fun/docs/django/ru/3.1/topics/migrations/)

[django-admin makemigrations](https://django.fun/docs/django/ru/3.1/ref/django-admin/#makemigrations) - Создает новые миграции на основе изменений, обнаруженных в ваших моделях. 

[migrate](https://django.fun/docs/django/ru/3.1/ref/django-admin/#django-admin-migrate) - отвечает за применение и отмену миграции.

[sqlmigrate](https://django.fun/docs/django/ru/3.1/ref/django-admin/#django-admin-sqlmigrate) - отображает операторы SQL для миграции.

[showmigrations](https://django.fun/docs/django/ru/3.1/ref/django-admin/#django-admin-showmigrations) - перечисляет миграции проекта и их статус.

######  Тестирование в Django [➦](https://django.fun/docs/django/ru/3.1/topics/testing/)

[django-admin test [test_label [test_label ...]]](https://django.fun/docs/django/ru/3.1/ref/django-admin/) - Запускает тесты для всех установленных приложений.

