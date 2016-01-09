FROM ubuntu:14.04
MAINTAINER Cristian Romo "cristian.g.romo@gmail.com"
# Based on imsky/haxe, which is under the MIT license.

RUN apt-get update && \
  apt-get install -y \
    curl \
    libgc-dev && \
  rm -rf /var/lib/apt/lists/*

ENV HAXE_VERSION 3.2.1
ENV HAXE_ROOT /opt/haxe/
RUN mkdir $HAXE_ROOT
RUN curl http://haxe.org/website-content/downloads/$HAXE_VERSION/downloads/haxe-$HAXE_VERSION-linux64.tar.gz | \
  tar xzf - --strip=1 -C $HAXE_ROOT

ENV HAXE_STD_PATH "$HAXE_ROOT/std/"
ENV PATH "$HAXE_ROOT:$PATH"

ENV NEKO_VERSION 2.0.0
ENV NEKOPATH /opt/neko
RUN mkdir $NEKOPATH
RUN curl http://nekovm.org/_media/neko-$NEKO_VERSION-linux64.tar.gz | \
  tar xzf - --strip=1 -C $NEKOPATH

ENV LD_LIBRARY_PATH $NEKOPATH
ENV PATH "$NEKOPATH:$PATH"

ENV HAXELIB_ROOT /opt/haxelib
RUN mkdir $HAXELIB_ROOT
RUN echo $HAXELIB_ROOT > /root/.haxelib
RUN cp /root/.haxelib /etc/

WORKDIR /source
CMD ["bash"]