FROM gcc:5
MAINTAINER Cristian Romo "cristian.g.romo@gmail.com"

ENV PATH /opt/wren:$PATH

RUN apt-get update && \
  apt-get install \
    git \
    -y && \
  rm -rf /var/lib/apt/lists/*
WORKDIR /opt
RUN git clone https://github.com/munificent/wren.git && \
  cd wren && \
  make

WORKDIR /source
CMD ["wren"]