## Kibana Installation

# Use Ubuntu as base image (not given version means it will use latest)
FROM ubuntu

# install software needed
RUN apt-get update
RUN apt-get install -y --no-install-recommends apt-utils
RUN apt-get install -y curl wget vim net-tools openssh-server

# download kibana version 6.1.1
RUN wget https://artifacts.elastic.co/downloads/kibana/kibana-6.1.1-amd64.deb

# install from the deb file
RUN dpkg -i kibana-6.1.1-amd64.deb

# copy the config into the container
COPY --chown=kibana:kibana kibana.yml /etc/kibana/

# start the services on run time
CMD service kibana start && bash

EXPOSE 5601
