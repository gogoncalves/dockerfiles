FROM tiangolo/uwsgi-nginx-flask:python3.6

COPY requirements.txt /tmp/
COPY . /app 

RUN pip install -U pip && pip install -r /tmp/requirements.txt

ADD contacts.txt .
ADD geojson .
ADD assets .

RUN apt-get -y update && apt-get install -y curl gnupg
RUN curl https://packages.microsoft.com/keys/microsoft.asc | apt-key add -
RUN curl https://packages.microsoft.com/config/ubuntu/22.04/prod.list > /etc/apt/sources.list.d/mssql-release.list
RUN apt-get -y update
RUN ACCEPT_EULA=Y apt-get install -y msodbcsql18
RUN apt-get update && apt-get install build-essential unixodbc-dev -y

WORKDIR /app

ENV NGINX_WORKER_PROCESSES auto