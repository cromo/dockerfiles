FROM gcc:4
MAINTAINER Cristian Romo "cristian.g.romo@gmail.com"

ENV PATH /opt/picoc:$PATH

RUN apt-get update && \
  apt-get install \
    git \
    -y && \
  rm -rf /var/lib/apt/lists/*
WORKDIR /opt
RUN git clone https://github.com/zsaleeba/picoc.git && \
  cd picoc && \
  make

WORKDIR /source
CMD ["picoc", "-i"]