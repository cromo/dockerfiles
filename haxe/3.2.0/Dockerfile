FROM ubuntu:14.04
MAINTAINER Cristian Romo "cristian.g.romo@gmail.com"
# Based on imsky/haxe, which is under the MIT license.

RUN apt-get update && \
  apt-get install -y \
    curl && \
  rm -rf /var/lib/apt/lists/*

ENV HAXE_VERSION 3.2.0
ENV HAXE_ROOT /opt/haxe/
RUN mkdir $HAXE_ROOT
RUN curl http://haxe.org/website-content/downloads/$HAXE_VERSION/downloads/haxe-$HAXE_VERSION-linux64.tar.gz | \
  tar xzf - --strip=1 -C $HAXE_ROOT

ENV HAXE_STD_PATH "$HAXE_ROOT/std/"
ENV PATH "$HAXE_ROOT:$PATH"

ENV HAXELIB_ROOT /opt/haxelib
RUN echo $HAXELIB_ROOT > /root/.haxelib
RUN cp /root/.haxelib /etc/

WORKDIR /source
CMD ["bash"]