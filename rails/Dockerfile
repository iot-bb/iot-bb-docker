FROM ruby:2.5.1

ENV RAILS_VERSION 5.2.0

COPY iot-bb-rails /usr/src/app
RUN gem install rails --version "$RAILS_VERSION"

EXPOSE 3000