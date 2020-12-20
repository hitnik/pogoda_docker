# pull official base image
FROM hitnik/python-sklearn-alpine:0.2

# set work directory
RUN mkdir -p /usr/src/app

WORKDIR /usr/src/app

#install git
RUN apk update && apk add git

#clone project from git

RUN git clone https://github.com/hitnik/date_api.git .
RUN git checkout master


# set environment variables
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

#RUN echo "http://dl-8.alpinelinux.org/alpine/edge/community" >> /etc/apk/repositories

## Add HDF5 support
#RUN apk add --no-cache --allow-untrusted --repository http://dl-3.alpinelinux.org/alpine/edge/testing hdf5 hdf5-dev
#RUN apk --no-cache --update-cache add gcc gfortran  build-base wget freetype-dev libpng-dev openblas-dev
#RUN ln -s /usr/include/locale.h /usr/include/xlocale.h

# install dependencies
RUN pip install --upgrade pip
RUN python3 -m pip install -r requirements.txt --no-cache-dir

RUN python -m nltk.downloader stopwords
RUN python -m nltk.downloader punkt