FROM python:3.8.2-buster

LABEL MAINTENER="hikaruright"

RUN apt-get update && apt-get install -y git nodejs npm
RUN npm install -g n
RUN n stable
RUN apt-get purge -y nodejs npm
# RUN exec $SHELL -l


RUN git clone https://github.com/inducer/relate 
COPY local_settings.py /relate

WORKDIR /relate

RUN pip install -r requirements.txt \
    && python manage.py migrate \
    # && python manage.py createsuperuser --username=$(whoami) \
    && npm install

EXPOSE 8000

ENTRYPOINT [ "python", "manage.py", "runserver", "0.0.0.0:8100" ]