FROM alpine

RUN apk add --no-cache \
    curl \
    bash \
    python

RUN adduser gcloud -D
USER gcloud

RUN curl https://sdk.cloud.google.com | bash

VOLUME ["/home/gcloud/.config/gcloud"]

ENTRYPOINT ["/home/gcloud/google-cloud-sdk/bin/gcloud"]

