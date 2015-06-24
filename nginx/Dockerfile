FROM nginx:1.9.2
MAINTAINER kmsheng "kmsh3ng@gmail.com"

RUN rm /bin/sh && ln -s /bin/bash /bin/sh

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update

RUN apt-get install -y php5 php5-fpm
