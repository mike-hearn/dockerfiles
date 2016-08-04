FROM node:slim

RUN npm install -g --ignore-scripts tldr
RUN tldr --update

ENTRYPOINT ["tldr"]
