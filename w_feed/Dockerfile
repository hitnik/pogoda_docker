# pull official base image
FROM python:3.8.1-alpine3.11

# set work directory
RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

#install git
RUN apk update && apk add git

#clone project from git
RUN git clone https://github.com/hitnik/pogoda_feed.git

#set work dirrectory inside project from git
WORKDIR /usr/src/app/pogoda_feed


# set environment variables
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

# install dependencies
RUN pip install --upgrade pip
RUN pip install -r requirements.txt --no-cache-dir

#make stsic dir
RUN mkdir -p ./static

#run migrations
RUN python manage.py migrate

#run collectstatic
RUN python manage.py collectstatic --no-input

