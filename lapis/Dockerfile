FROM cromo/moonscript
MAINTAINER Cristian Romo "cristian.g.romo@gmail.com"

# Wrong lua? https://github.com/leafo/lapis/issues/102

RUN apt-get update && \
  apt-get install -y \
    curl \
    libpcre3-dev \
    libssl-dev && \
  rm -rf /var/lib/apt/lists/*
RUN luarocks install lapis && \
  luarocks install LuaCrypto
RUN curl -O http://openresty.org/download/ngx_openresty-1.7.10.1.tar.gz && \
  tar xzvf ngx_openresty-1.7.10.1.tar.gz && \
  cd ngx_openresty-1.7.10.1 && \
  ./configure && \
  make install && \
  cd .. && \
  rm -rf ngx_openresty-1.7.10.1 ngx_openresty-1.7.10.1.tar.gz

WORKDIR /source
CMD ["bash"]