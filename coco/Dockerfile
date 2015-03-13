FROM node
MAINTAINER Cristian Romo "cristian.g.romo@gmail.com"

RUN apt-get update && \
  apt-get install -y \
    git && \
  rm -rf /var/lib/apt/lists/*

RUN npm i -g coco && \
  git clone --depth=1 git://github.com/satyr/coco.git && \
  cd coco && \
  bin/coke i && \
  cd .. && \
  rm -rf coco

RUN mkdir /source
WORKDIR /source
CMD ["coco", "-i"]