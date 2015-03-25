FROM python:2
MAINTAINER Cristian Romo "cristian.g.romo@gmail.com"

RUN apt-get update && \
  apt-get install -y \
    omniidl \
    omniidl-python \
    omniorb-nameserver \
    python-omniorb \
    python-omniorb-doc && \
  rm -rf /var/lib/apt/lists/*
RUN pip install hy
RUN cp -r /usr/lib/python2.7/dist-packages/* /usr/local/lib/python2.7/site-packages

WORKDIR /source
CMD ["hy"]