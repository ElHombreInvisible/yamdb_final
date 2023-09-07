# Проект запуска docker-compose
Позволяет запустить сервис API YAMDB с помощью технологии Docker
## Инструкции по запуску:
- установить Docker
- склонировать проект ```git clone <project_link>```
- настроить .env-файл в директории infra/
- выполнить команду ```docker-compose up```
- применить миграции ```docker-compose exec web python manage.py migrate```
- создать суперпользователя сервиса YAMDB командой ```docker-compose exec web python manage.py createsuperuser```
- собрать файлы статики для сервера nginx ```docker-compose exec web python manage.py collectstatic --no-input```
# Для переноса базы данных:
- выполнить команду для дампа текущей базы данных```docker-compose exec web python manage.py dumpdata > fixtures.json```
- копировать базу данных в папку /api_yamdb/
- заполнить базу данных из дампа командой ```docker-compose exec web python manage.py loaddata fixtures.json```

## Status
![worflow status badge](https://github.com/elhombreinvisible/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg)
