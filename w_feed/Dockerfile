# pull official base image
FROM hitnik/python-postgres-alpine

ADD https://api.github.com/repos/hitnik/pogoda_feed/git/refs/heads/master version.json

# set work directory
RUN mkdir -p /usr/src/app

WORKDIR /usr/src/app


#install git
RUN apk update && apk add git
RUN apk add build-base

#clone project from git

RUN git clone  https://github.com/hitnik/pogoda_feed.git .
RUN git checkout master


# set environment variables
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1


#RUN apk add gcc
#RUN apk add --no-cache libressl-dev musl-dev libffi-dev



# install dependencies
RUN pip install -U setuptools pip
RUN \
 python3 -m pip install -r requirements.txt --no-cache-dir && \
 apk --purge del .build-deps

RUN python -m nltk.downloader punkt

#make stsic dir
RUN mkdir -p ./static

#run migrations
#RUN python manage.py migrate


