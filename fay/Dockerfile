FROM haskell
MAINTAINER Cristian Romo "cristian.g.romo@gmail.com"

RUN cabal update && \
  cabal install cpphs && \
  cabal install fay fay-base

CMD ["bash"]