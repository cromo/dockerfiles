FROM cromo/haxe:3.2.0
MAINTAINER Cristian Romo "cristian.g.romo@gmail.com"

RUN apt-get update && \
  apt-get install -y \
    php5 && \
  rm -rf /var/lib/apt/lists/*

WORKDIR /source
CMD ["bash"]