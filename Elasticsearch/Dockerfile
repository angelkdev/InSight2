## Elasticsearch Installation

# Use Ubuntu as base image (not given version means it will use latest)
FROM ubuntu

# install dependencies
RUN apt-get update
RUN apt-get install -y --no-install-recommends apt-utils
RUN apt-get install -y curl wget vim net-tools openssh-server openjdk-8-jre

# download elasticsearch version 6.1.1
RUN wget https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-6.1.1.deb

# install elasticsearch from the deb file
RUN dpkg -i elasticsearch-6.1.1.deb

# copy the config into the container
COPY --chown=elasticsearch:elasticsearch elasticsearch.yml /etc/elasticsearch/
COPY --chown=elasticsearch:elasticsearch jvm.options /etc/elasticsearch/

#start the services on run time
CMD service elasticsearch start && bash

EXPOSE 9200
EXPOSE 9300
