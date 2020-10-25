FROM nginx:1.17.2-alpine

RUN rm /etc/nginx/conf.d/default.conf
#COPY nginx.conf /etc/nginx/conf.d
COPY ./data /etc/nginx/

#RUN apk add openssl
#RUN cd /etc/nginx/certs/
#RUN su
#RUN openssl req -new -x509 -days 9999 -nodes -subj /C=RU/O=My\ site/CN=hazard/emailAddress=hitnik@hazard -out hazard.pem -keyout hazard.key