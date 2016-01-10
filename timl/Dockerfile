FROM alpine:3.3
MAINTAINER Cristian Romo "cristian.g.romo@gmail.com"

RUN apk add --update \
    git \
    vim \
    wget && \
  rm -rf /var/cache/apk/*
RUN mkdir -p ~/.vim/autoload ~/.vim/bundle && \
  wget -O ~/.vim/autoload/pathogen.vim https://tpo.pe/pathogen.vim && \
  >~/.vimrc echo 'execute pathogen#infect()' && \
  git clone git://github.com/tpope/timl.git ~/.vim/bundle/timl

CMD ["vim", "-c", "TLrepl"]