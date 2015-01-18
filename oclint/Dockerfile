FROM ubuntu:trusty
MAINTAINER Cristian Romo "cristian.g.romo@gmail.com"

RUN apt-get update && \
  apt-get install -y \
    curl && \
  rm -rf /var/lib/apt/lists/*
RUN curl -O http://archives.oclint.org/releases/0.8/oclint-0.8.1-x86_64-linux-3.13.0-35-generic.tar.gz && \
  tar xf oclint-0.8.1-x86_64-linux-3.13.0-35-generic.tar.gz -C /opt && \
  rm oclint-0.8.1-x86_64-linux-3.13.0-35-generic.tar.gz

ENV PATH /opt/oclint-0.8.1/bin:$PATH

RUN mkdir /source
WORKDIR /source
CMD ["bash"]