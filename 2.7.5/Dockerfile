FROM ruby:2.7.5-alpine as builder

# TODO: Use repository version of jemalloc when available
RUN wget -O - https://github.com/jemalloc/jemalloc/releases/download/5.3.0/jemalloc-5.3.0.tar.bz2 | tar -xj && \
    cd jemalloc-5.3.0 && \
    ./configure && \
    make && \
    make install

# jemalloc is now installed in /usr/local/lib/libjemalloc.so.2
