FROM cromo/haxe:3.2.0-cpp
MAINTAINER Cristian Romo "cristian.g.romo@gmail.com"

RUN curl --location --output devkitARMupdate.pl \
  'http://downloads.sourceforge.net/project/devkitpro/Automated%20Installer/devkitARMupdate.pl?r=http%3A%2F%2Fsourceforge.net%2Fprojects%2Fdevkitpro%2Ffiles%2FAutomated%2520Installer%2F&ts=1436590934&use_mirror=iweb'

ENV DEVKITPRO /opt/devkitPro
ENV DEVKITARM $DEVKITPRO/devkitARM

RUN apt-get update && \
  apt-get install -y \
    automake \
    autotools-dev \
    bzip2 \
    git \
    make \
    perl \
    wget && \
  rm -rf /var/lib/apt/lists/*
RUN perl devkitARMupdate.pl && \
  rm ./devkitARMupdate.pl ./*.tar.bz2

RUN git clone https://github.com/devkitPro/3dstools.git /opt/3dstools && \
  cd /opt/3dstools && \
  ./autogen.sh && \
  ./configure --prefix=$DEVKITARM && \
  make && \
  make install && \
  cd / && \
  rm -rf /opt/3dstools

# Pull down the hxcpp fork that contains support for devkitARM and build the
# necessary neko bytecode files. hxcpp.n always needs to be built for
# development builds, and build.n needs to be rebuilt to include the
# devkitarm3ds target.
# After that, rebuild hxcpp for 3DS.
ENV HXCPP_DEV /opt/hxcpp
RUN git clone https://github.com/cromo/hxcpp.git $HXCPP_DEV && \
  haxelib dev hxcpp $HXCPP_DEV && \
  cd $HXCPP_DEV/tools/hxcpp && \
  haxe compile.hxml && \
  cd $HXCPP_DEV/tools/build && \
  haxe compile.hxml && \
  cd $HXCPP_DEV/project && \
  neko build.n static-devkitarm3ds

# Pull down the ctrulib fork that has the work in progress pthread compatibility
# layer. `make install` builds and installs it into `$DEVKITPRO/libctru`.
ENV CTRU_DEV /opt/ctrulib
RUN git clone https://github.com/zeta0134/ctrulib.git $CTRU_DEV && \
  cd $CTRU_DEV/libctru && \
  make install

WORKDIR /source
CMD ["bash"]
