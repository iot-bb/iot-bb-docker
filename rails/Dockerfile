FROM ruby:2.5.1

ENV APP_HOME /usr/src/app

RUN apt-get update && apt-get install -y nodejs --no-install-recommends && rm -rf /var/lib/apt/lists/*

WORKDIR $APP_HOME
COPY iot-bb-rails $APP_HOME
RUN bundle install

EXPOSE 3000