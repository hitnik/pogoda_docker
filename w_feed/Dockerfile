# pull official base image
FROM python:3.8.1-alpine3.11

# set work directory
RUN mkdir -p /usr/src/app

WORKDIR /usr/src/app

#install git
RUN apk update && apk add git
RUN apk add nano

#clone project from git
RUN git clone https://github.com/hitnik/pogoda_feed.git .

RUN git checkout

# set environment variables
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

# install dependencies
RUN pip install --upgrade pip
RUN pip install -r requirements.txt --no-cache-dir

#make stsic dir
RUN mkdir -p ./static

##run migrations
#RUN python manage.py migrate
#
##load fixtures
#RUN python manage.py loaddata hazard_feed/fixtures/hazard_levels.json
#
##run collectstatic
#RUN python manage.py collectstatic --no-input