FROM debian:jessie
MAINTAINER Cristian Romo "cristian.g.romo@gmail.com"

# These dictate where to install devkitPro/ARM and dictate where they are found
# in project makefiles.
ENV DEVKITPRO /opt/devkitPro
ENV DEVKITARM $DEVKITPRO/devkitARM

ADD devkitARMupdate.pl devkitARMupdate.pl
RUN apt-get update && \
  apt-get install -y \
    bzip2 \
    make \
    perl \
    wget && \
  rm -rf /var/lib/apt/lists/*
RUN perl devkitARMupdate.pl && \
  rm /devkitARMupdate.pl /*.tar.bz2

RUN mkdir /source
WORKDIR /source
CMD ["bash"]
