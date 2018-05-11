FROM node:8.10-alpine
LABEL MAINTAINER "Lucas Montiel <lcsmontiel@gmail.com>"

ADD ./wrapdocker /usr/local/bin/wrapdocker

RUN apk --no-cache add \
    docker \
    git \
    python \
    py-pip \
  && pip install awscli \
  && apk --purge -v del py-pip \
  && rm -rf /var/cache/apk/* \
  && chmod +x /usr/local/bin/wrapdocker

VOLUME /var/lib/docker

CMD ["wrapdocker"]