FROM alpine:3.3
MAINTAINER Cristian Romo "cristian.g.romo@gmail.com"

ENV PATH /opt/gherkin:$PATH

RUN apk add --update bash && \
  rm -rf /var/cache/apk/* && \
  mkdir -p /opt/gherkin
ADD gherkin /opt/gherkin/gherkin
ADD core.gk /opt/gherkin/core.gk

WORKDIR /source
CMD ["gherkin", "-l", "/opt/gherkin/core.gk", "-r"]