FROM python:3.7-slim

LABEL name='API YamDB Yandex Practicum' version=1.0

WORKDIR /app

COPY . .

RUN pip3 install -r requirements.txt --no-cache-dir

CMD ["gunicorn", "api_yamdb.wsgi:application", "--bind", "0:8000" ]