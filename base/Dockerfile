FROM debian:stable-slim

ENV DEBIAN_FRONTEND=noninteractive \
    NPM_CONFIG_LOGLEVEL=info \
    NODE_VERSION=5.12.0 \
    YARN_VERSION=0.21.3 \
    PATH=$PATH:./node_modules/.bin

RUN \
    # Create node user \
    groupadd --gid 1000 node \
    && useradd --uid 1000 --gid node --shell /bin/bash --create-home node \
    # Install wget \
    && apt-get update -yqq \
    && apt-get install -yqq wget bzip2 \
    && rm -rf /var/lib/apt/lists/* \
    # Install nodejs \
    && wget -q "https://nodejs.org/dist/v$NODE_VERSION/node-v$NODE_VERSION-linux-x64.tar.gz" \
    && tar -xzf "node-v$NODE_VERSION-linux-x64.tar.gz" -C /usr/local --strip-components=1 \
    && rm "node-v$NODE_VERSION-linux-x64.tar.gz" \
    && ln -s /usr/local/bin/node /usr/local/bin/nodejs \
    # Install yarn \
    && wget -qO yarn.js "https://yarnpkg.com/downloads/$YARN_VERSION/yarn-legacy-$YARN_VERSION.js" \
    && mv yarn.js /usr/local/bin/yarn \
    && chmod +x /usr/local/bin/yarn

WORKDIR /usr/src/app

# Mimic'ing the official node image

CMD [ "node" ]

