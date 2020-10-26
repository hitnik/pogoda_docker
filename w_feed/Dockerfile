# pull official base image
FROM python:3.8-alpine

# set work directory
RUN mkdir -p /usr/src/app

WORKDIR /usr/src/app

ADD https://api.github.com/repos/hitnik/pogoda_feed/git/refs/heads/master version.json

#install git
RUN apk update && apk add git

#clone project from git

RUN git clone https://github.com/hitnik/pogoda_feed.git .
RUN git checkout master


# set environment variables
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1


#RUN apk add gcc
#RUN apk add --no-cache libressl-dev musl-dev libffi-dev



# install dependencies
RUN pip install --upgrade pip
RUN \
 apk add --no-cache postgresql-libs && \
 apk add --no-cache --virtual .build-deps gcc musl-dev postgresql-dev && \
 apk add --no-cache libressl-dev libffi-dev &&\
 python3 -m pip install -r requirements.txt --no-cache-dir && \
 apk --purge del .build-deps

RUN python -m nltk.downloader punkt

#make stsic dir
RUN mkdir -p ./static

#run migrations
RUN python manage.py migrate


