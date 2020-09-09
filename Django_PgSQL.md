#### ✓ Настройка Django для работы с PostgreSQL

▪ sudo apt-get install libpq-dev python-dev

▪ sudo apt-get install postgresql postgresql-contrib

▪ pip install psycopg2 или pip install psycopg2-binary

#### ✓ Создание базы данных и пользователя PostgreSQL

▪ Войти в терминал. Запустить оболочку PostgreSQL

    sudo -u postgres psql

▪ Создать базу данных.

    CREATE DATABASE myproject;
    
▪ Создать пользователя, задать пароль.
       
    CREATE USER myprojectuser WITH PASSWORD 'password';     

▪ Настроить созданную роль.
    
    ALTER ROLE myprojectuser SET client_encoding TO 'utf8';
    ALTER ROLE myprojectuser SET default_transaction_isolation TO 'read committed';
    ALTER ROLE myprojectuser SET timezone TO 'UTC';
    

▪ Дать пользователю доступ для администрирования новой базы данных.

    GRANT ALL PRIVILEGES ON DATABASE myproject TO myprojectuser;

▪ \q

#### ✓ Настроить базу данных  в settings.py

    DATABASES = {
        'default': {
            'ENGINE': 'django.db.backends.postgresql_psycopg2',
            'NAME': 'myproject',
            'USER': 'myprojectuser',
            'PASSWORD': 'password',
            'HOST': 'localhost',
            'PORT': '',
        }
    }