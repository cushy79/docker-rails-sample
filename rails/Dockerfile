FROM ruby:2.3.1-alpine
ENV BUILD_PACKAGES="curl-dev ruby-dev build-base bash" \
    DEV_PACKAGES="zlib-dev libxml2-dev libxslt-dev tzdata yaml-dev mysql-dev" \
    RUBY_PACKAGES="ruby-json yaml nodejs"

RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

RUN apk add --no-cache --update \
    $BUILD_PACKAGES \
    $DEV_PACKAGES \
    $RUBY_PACKAGES

ADD Gemfile /usr/src/app/Gemfile
ADD Gemfile.lock /usr/src/app/Gemfile.lock
RUN bundle install
ADD . /usr/src/app
