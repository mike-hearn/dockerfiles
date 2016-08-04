FROM golang:alpine

RUN apk add --no-cache git
RUN go get -v github.com/spf13/hugo

VOLUME ["/data"]
WORKDIR /data

ENTRYPOINT ["hugo"]
