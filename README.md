Перед запуском проекта необходимо выполнить следующие действия:
1. Заполнить своими данными файл .env.samle и пересохранить его как .env
2. Запустить redis сервер.
3. Создать БД в PSQL и указать наименование БД в файле .env 
   Для работы с БД произвести настройки в PostgreSQL сервере, в файле pg_hba.conf 
   # TYPE  DATABASE        USER            ADDRESS                 METHOD

    # "local" is for Unix domain socket connections only
    local   all             all                                     trust
    # IPv4 local connections:
    host    all             all             127.0.0.1/32            trust
    # IPv6 local connections:
    host    all             all             ::1/128                 trust
    # Allow replication connections from localhost, by a user with the
    # replication privilege.
    local   replication     all                                     trust
    host    replication     all             127.0.0.1/32            trust
    host    replication     all             ::1/128                 trust
4. Командой python manage.py loaddata загрузить информацию в БД из файла mailing_data.json