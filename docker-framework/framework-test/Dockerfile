FROM ubuntu:5001/docker-framework:latest

MAINTAINER Jon Roquelaure jonathanr@jfrog.com

COPY ui/ /usr/share/nginx/html/

RUN sed -i "s+http://localhost:9000/+/ws/+g" /usr/share/nginx/html/frogsui/app/app.js
ADD jar/*.jar /ws/frogsws.jar
COPY conf/ws.conf /etc/nginx/conf.d/ws.conf


EXPOSE 8000 9000
CMD service nginx restart && java -jar /ws/frogsws.jar && /bin/bash
