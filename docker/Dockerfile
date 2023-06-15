FROM python:3.9.0a2-alpine3.10

ENV LANG C.UTF-8

COPY packages/snyk-linux /usr/local/bin/snyk-linux

ENV PATH /usr/src/app/node_modules/.bin:${PATH}

RUN apk add  --no-cache --repository http://dl-cdn.alpinelinux.org/alpine/v3.7/main/ nodejs=8.9.3-r1
RUN apk add --update curl bash
RUN apk update && \
    apk upgrade && \
    apk add --no-cache \
        docker \
        git \
        nodejs && \
    pip install requests && \
    npm install codefresh -g && \
    npm install snyk -g && \
    chmod +x /usr/local/bin/snyk-linux

COPY scripts/snyk-cli.py /snyk-cli.py

CMD [""]
