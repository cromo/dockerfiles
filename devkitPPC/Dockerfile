FROM debian:wheezy
MAINTAINER Cristian Romo "cristian.g.romo@gmail.com"

# These dictate where to install devkitPro/PPC and dictate where they are found
# in project makefiles.
ENV DEVKITPRO /opt/devkitPro
ENV DEVKITPPC $DEVKITPRO/devkitPPC

ADD devkitPPCupdate.pl devkitPPCupdate.pl
RUN apt-get update && \
  apt-get install -y \
    bzip2 \
    make \
    perl \
    wget && \
  rm -rf /var/lib/apt/lists/*
RUN perl devkitPPCupdate.pl && \
  rm /devkitPPCupdate.pl /*.tar.bz2

RUN mkdir /source
WORKDIR /source
CMD ["bash"]