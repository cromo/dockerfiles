FROM debian:wheezy
MAINTAINER Cristian Romo "cristian.g.romo@gmail.com"

RUN apt-get update && \
  apt-get install \
    graphviz \
    -y && \
  rm -rf /var/lib/apt/lists/*

WORKDIR /source
CMD ["bash"]