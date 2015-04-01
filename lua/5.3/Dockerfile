FROM alpine:3.1
MAINTAINER Cristian Romo "cristian.g.romo@gmail.com"

ENV LUA_VERSION 5.3.0

RUN apk --update add build-base && \
  wget http://www.lua.org/ftp/lua-$LUA_VERSION.tar.gz && \
  gunzip lua-$LUA_VERSION.tar.gz && \
  tar xf lua-$LUA_VERSION.tar && \
  cd lua-$LUA_VERSION && \
  make posix && \
  make install && \
  cd .. && \
  rm -rf lua-$LUA_VERSION lua-$LUA_VERSION.tar && \
  apk del build-base && \
  rm -rf /var/cache/apk/*

WORKDIR /source
CMD ["lua"]