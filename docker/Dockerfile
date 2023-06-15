FROM python:3.9.17-alpine3.18

ENV LANG C.UTF-8

COPY packages/snyk-linux /usr/local/bin/snyk-linux

ENV PATH /usr/src/app/node_modules/.bin:${PATH}

RUN apk add nodejs --update-cache --repository http://dl-cdn.alpinelinux.org/alpine/edge/main --allow-untrusted
RUN apk add --update curl bash
RUN apk update && \
    apk upgrade && \
    apk add --no-cache \
        docker \
        git \
        npm \
        nodejs && \
    pip install requests && \
    npm install codefresh -g && \
    npm install snyk -g && \
    chmod +x /usr/local/bin/snyk-linux

COPY scripts/snyk-cli.py /snyk-cli.py

CMD [""]
