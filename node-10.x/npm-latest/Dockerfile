FROM ubuntu:18.04

LABEL maintainer = "Matt Banner <matt@banner.wtf>"

ENV DEBIAN_FRONTEND noninteractive

ENV NODE_VERSION 10.x
ENV NPM_VERSION latest

RUN \
    apt-get update && \
    apt-get install -y \
        software-properties-common \
        curl && \
    curl -sL https://deb.nodesource.com/setup_$NODE_VERSION -o nodesource_setup.sh && \
    bash ./nodesource_setup.sh && \
    apt-get update && \
    apt-get install -y \
        nodejs && \
    npm i -g npm@$NPM_VERSION && \
    useradd user && \
    apt-get remove -y software-properties-common curl && \
    apt-get autoremove -y && \
    rm -rf /var/lib/apt/lists/* /var/cache/apt/*

VOLUME ["/app"]
WORKDIR /app

USER user

CMD ["-"]
ENTRYPOINT ["npm", "--ansi"]
