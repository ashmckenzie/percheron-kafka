FROM gliderlabs/alpine:latest
MAINTAINER ash@the-rebellion.net

ENV HOME /root
ENV TERM ansi
ENV PATH /usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin

ADD ./config/repositories /etc/apk/
ADD ./config/supervisord.conf /etc/

RUN apk add --update-cache supervisor git bash openssl-dev ca-certificates
RUN apk add --update-cache openjdk7-jre-base

RUN mkdir -p /etc/supervisor.d
