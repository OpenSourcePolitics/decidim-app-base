FROM ruby:2.7.5-alpine as builder

# TODO: Use repository version of jemalloc when available
RUN apk add --no-cache --update nodejs yarn tzdata git icu-dev libpq-dev build-base proj proj-dev postgresql-client imagemagick && \
    gem install bundler:2.4.9 && \
    wget -O - https://github.com/jemalloc/jemalloc/releases/download/5.3.0/jemalloc-5.3.0.tar.bz2 | tar -xj && \
    cd jemalloc-5.3.0 && \
    ./configure && \
    make && \
    make install

# jemalloc is now installed in /usr/local/lib/libjemalloc.so.2