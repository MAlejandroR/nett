FROM ubuntu
ENV DEBIAN_FRONTEND="noninteracive"
ADD . /app

RUN apt-get update

RUN apt-get install -y apache2
RUN apt-get install -y php
RUN apt-get install -y libapache2-mod-php

RUN apt-get install -y mysql-client mysql-server

  # esto debería iniciar tres procesos, mysql y ssh 
  # en segundo plano y node app en primer plano 
  # no es tremendamente bonito? <3 
CMD service mysql start  & apachectl start & /bin/bash