FROM node:14.7-alpine

# set work directory
RUN mkdir -p /usr/src/app

WORKDIR /usr/src/app

#install git
RUN apk update && apk add git

#clone project from git
RUN git clone https://github.com/hitnik/pogoda_ui.git .
RUN git checkout master

# copy entrypoint.sh
COPY ./entrypoint.sh /usr/src/app/entrypoint.sh

# Build args
ARG API_HOST

# Environment vars
ENV API_HOST=$API_HOST


#install node dependencies
RUN npm install

#install HTTp server
RUN npm install --global http-server