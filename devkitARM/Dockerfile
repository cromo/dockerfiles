FROM debian:wheezy
MAINTAINER Cristian Romo "cristian.g.romo@gmail.com"

# These dictate where to install devkitPro/ARM and dictate where they are found
# in project makefiles.
ENV DEVKITPRO /opt/devkitPro
ENV DEVKITARM $DEVKITPRO/devkitARM

ADD devkitARMupdate.pl devkitARMupdate.pl
RUN apt-get update && \
  apt-get install -y perl wget bzip2 make && \
  rm -rf /var/lib/apt/lists/*
# This call to sed inserts a line to force downloading r42. For some reason, the
# Windows installer is labeled r43, but there is no r43 for Linux or Mac. The
# latest official release on devkitPro.org is r42.
RUN sed -i '201i $newFiles{devkitARM} =~ s/r43/r42/;' devkitARMupdate.pl && \
  perl devkitARMupdate.pl && \
  rm /*.tar.bz2

VOLUME ["/source"]
WORKDIR /source
CMD ["bash"]
