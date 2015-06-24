FROM ubuntu:14.04

MAINTAINER kmsheng "kmsh3ng@gmail.com"

RUN rm /bin/sh && ln -s /bin/bash /bin/sh

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update

RUN apt-get install -y nodejs npm git git-core

RUN ln -s `which nodejs` /usr/bin/node

RUN npm install -g pouchdb-server

WORKDIR /database
