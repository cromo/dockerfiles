FROM cromo/haxe:3.2.1
MAINTAINER Cristian Romo "cristian.g.romo@gmail.com"
# Based on imsky/haxe, which is under the MIT license.

RUN apt-key adv --keyserver pgp.mit.edu --recv-keys 3FA7E0328081BFF6A14DA29AA6A19B38D3D831EF && \
  echo "deb http://download.mono-project.com/repo/debian wheezy main" > /etc/apt/sources.list.d/mono-xamarin.list
RUN apt-get update && \
  apt-get install -y \
    mono-devel && \
  rm -rf /var/lib/apt/lists/*

RUN haxelib install hxcs

WORKDIR /source
CMD ["bash"]