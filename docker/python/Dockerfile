FROM python:3.7

RUN mkdir /var/www
WORKDIR /var/www
COPY ./docker/uwsgi/uwsgi.ini ./

RUN mkdir /var/www/app
WORKDIR /var/www/app

COPY ./app/Pipfile ./

RUN apt-get update && \
    apt-get -y install python3-pip && \
    pip install --upgrade pip && \
    pip install pipenv && \
    pipenv install

CMD ["pipenv", "run", "uwsgi", "--ini", "/var/www/uwsgi.ini"]