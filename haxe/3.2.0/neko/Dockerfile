FROM cromo/haxe:3.2.0
MAINTAINER Cristian Romo "cristian.g.romo@gmail.com"
# Based on imsky/haxe, which is under the MIT license.

RUN apt-get update && \
  apt-get install -y \
    libgc-dev && \
  rm -rf /var/lib/apt/lists/*

ENV NEKO_VERSION 2.0.0
ENV NEKOPATH /opt/neko
RUN mkdir $NEKOPATH
RUN curl http://nekovm.org/_media/neko-$NEKO_VERSION-linux64.tar.gz | \
  tar xzf - --strip=1 -C $NEKOPATH

ENV LD_LIBRARY_PATH $NEKOPATH
ENV PATH "$NEKOPATH:$PATH"