[❰❰❰](https://github.com/L1quide/CheatSeets/blob/master/Django_main.md)  [HOME](https://github.com/L1quide/CheatSeets/blob/master/README.md)

#### ✓ Установить Django

▪ pip install Django

#### ✓ Создать проект Django

▪ mkdir libra

▪ cd libra

▪ django-admin startproject libra

▪ cd libra

#### ✓ Создать приложение libra

▪ python manage.py startapp catalog

#### ✓ Зарегистрировать приложение в settings.py

▪ libra/libra/libra/settings.py ➜ INSTALLED_APPS ➜ 'catalog.apps.CatalogConfig'

#### ✓ Создать суперюзера

▪ python manage.py createsuperuser
    
#### ✓ Подготовить/Выполнить миграцию

▪ python manage.py makemigrations - подготовить созданную базу данных к миграции.

▪ python manage.py migrate - выполнить миграцию.