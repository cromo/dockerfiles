FROM cromo/devkitarm
MAINTAINER Cristian Romo "cristian.g.romo@gmail.com"

RUN apt-get update && \
  apt-get install -y \
    git && \
  rm -rf /var/lib/apt/lists/*
WORKDIR /opt/devkitPro
RUN git clone --depth=1 https://github.com/smealum/ctrulib.git
WORKDIR /opt/devkitPro/ctrulib/libctru
RUN make && \
  make install

WORKDIR /source
CMD ["bash"]
