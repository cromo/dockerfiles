FROM gcc
MAINTAINER Cristian Romo "cristian.g.romo@gmail.com"

RUN apt-get update && \
  apt-get install -y \
    git && \
  rm -rf /var/lib/apt/lists/*
ENV LD_RUN_PATH /usr/local/lib64/
RUN git clone https://github.com/bengardner/uncrustify.git && \
  cd uncrustify && \
  ./configure && \
  make install && \
  cd .. && \
  rm -rf uncrustify

RUN mkdir /source
WORKDIR /source
CMD ["bash"]