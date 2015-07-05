FROM cromo/haxe:3.2.0
MAINTAINER Cristian Romo "cristian.g.romo@gmail.com"
# Based on imsky/haxe, which is under the MIT license.

RUN apt-get update && \
  apt-get install -y \
    default-jdk && \
  rm -rf /var/lib/apt/lists/*

RUN haxelib install hxjava

WORKDIR /source
CMD ["bash"]