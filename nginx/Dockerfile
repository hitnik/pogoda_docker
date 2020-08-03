FROM nginx:1.17.2-alpine

RUN rm /etc/nginx/conf.d/default.conf
COPY nginx.conf /etc/nginx/conf.d

# # set work directory
# RUN mkdir -p /usr/src/app

# WORKDIR /usr/src/app

# #install git
# RUN apk update && apk add git

# # # remove dist directory
# # RUN rm -rf ./dist


# #clone project from git
# RUN git clone https://github.com/hitnik/pogoda_ui.git .
# RUN git checkout master

# # remove dist directory
# RUN mkdir dist

# #install NPM
# RUN apk add npm


# #install node dependencies
# RUN npm install

# #build production react app
# RUN npm run-script build