FROM golang:alpine

RUN apk add --no-cache git

RUN adduser hugo -D
USER hugo

RUN go get -v github.com/spf13/hugo

VOLUME ["/data"]
WORKDIR /data

ENTRYPOINT ["hugo"]
