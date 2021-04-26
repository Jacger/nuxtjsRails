FROM ruby:latest

RUN apt-get update && \
    apt-get install -y curl apt-transport-https wget && \
    curl -sL https://deb.nodesource.com/setup_14.x | bash - && \
    apt-get install -y --no-install-recommends \
    nodejs \
    libmagic-dev \
    libpq-dev && \
    rm -rf /var/lib/apt/lists/*

RUN npm install -g yarn
RUN mkdir /app

ENV GEM_HOME /app/vendor/bundle
ENV BUNDLE_PATH /app/vendor/bundle
ENV BUNDLE_BIN /app/vendor/bundle/bin
ENV PATH $BUNDLE_BIN:$BUNDLE_PATH/gems/bin:$PATH

COPY ./docker-entrypoint.sh /
RUN chmod +x /docker-entrypoint.sh

WORKDIR /app
