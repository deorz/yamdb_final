![YamDB_workflow](https://github.com/deorz/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg)

# Infrastructire for API YamDB

#### Description:

Это проект API YamDB с подготовленной инфраструктурой для развёртывания его в
docker контейнере и деплоя на сервер

Расположен по адресу: http://84.201.163.148/api/v1/

#### Stack:

- Python 3.8
- Django Framework 2.2.16
- Django Rest Framework 3.12.4
- gunicorn


#### Infrastructure:
- docker
- nginx for docker
- postgresql db in docker

#### Installation:

1. Install and activate virtual environment(venv) then:

   ```shell
   cd infra/
   ```
   
   In .env file you have to set up variables for DB connection and Django Secret key e.g.:
   ```
   SECRET_KEY=DJANGO_APP_SECRET_KEY
   HOST=YOUR_DB_SERVER_HOST
   ...
   DB_NAME=YOUR_DB_NAME
   ```

   ```shell
   docker-compose up -d --build
   ```

2. Make migrations in docker container:

   ```shell
   docker-compose exec web python manage.py migrate
   ```

3. Collect all static in one directory:

   ```shell
   docker-compose exec web collectstatic --no-input
   ```


4. Enjoy!


#### If you wanna stop container and discard all changes:

   ```shell
   docker-compose down -v
   ```

------

​ Author: deorz