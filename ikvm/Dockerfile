FROM mono:4
MAINTAINER Cristian Romo "cristian.g.romo@gmail.com"

ENV IKVM_VERSION 7.2.4630.5

RUN apt-get update && \
  apt-get install \
    openjdk-7-jdk \
    unzip \
    -y && \
  rm -rf /var/lib/apt/lists/*
WORKDIR /opt
RUN curl -O http://skylineservers.dl.sourceforge.net/project/ikvm/ikvm/$IKVM_VERSION/ikvmbin-$IKVM_VERSION.zip && \
  unzip ikvmbin-$IKVM_VERSION.zip && \
  rm ikvmbin-$IKVM_VERSION.zip && \
  mv ikvm-$IKVM_VERSION ikvm
RUN >/usr/local/bin/ikvm echo 'mono /opt/ikvm/bin/ikvm.exe "$@"' && \
  chmod +x /usr/local/bin/ikvm && \
  >/usr/local/bin/ikvmc echo 'mono /opt/ikvm/bin/ikvmc.exe "$@"' && \
  chmod +x /usr/local/bin/ikvmc && \
  >/usr/local/bin/ikvmstub echo 'mono /opt/ikvm/bin/ikvmstub.exe "$@"' && \
  chmod +x /usr/local/bin/ikvmstub

WORKDIR /source
CMD ["bash"]