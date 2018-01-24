FROM alpine:3.7
MAINTAINER Tin Lam <tin@irrational.io>

RUN apk update \
    && apk add --update curl \
    && rm -rf /var/cache/apk/*

CMD ["curl"]
