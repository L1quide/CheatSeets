[❰❰❰](https://github.com/L1quide/CheatSeets/blob/master/Django_main.md)  [HOME](https://github.com/L1quide/CheatSeets/blob/master/README.md)


Типы полей

[✓ Справочник типов полей](https://django.fun/docs/django/ru/3.0/ref/models/fields/#model-field-types)

Автоматические поля первичного ключа

Если вы хотите указать собственный первичный ключ, укажите primary_key = True в одном из ваших полей. Если Django увидит, что вы явно указали Field.primary_key, он не добавит автоматический столбец id.

Каждой модели требуется ровно одно поле primary_key = True (либо объявлено явно, либо добавлено автоматически).

