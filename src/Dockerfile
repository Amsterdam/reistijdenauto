FROM amsterdam/python
MAINTAINER datapunt@amsterdam.nl

ENV PYTHONUNBUFFERED 1

WORKDIR /app


##  # CI hook - see .jenkins/README.TXT
COPY .jenkins/import /.jenkins-import/
COPY .jenkins/docker-migrate.sh /app/

COPY requirements.txt /app/
RUN pip install --no-cache-dir -r requirements.txt
COPY . /app/

USER datapunt

RUN export DJANGO_SETTINGS_MODULE=reistijdenauto.settings

CMD uwsgi

