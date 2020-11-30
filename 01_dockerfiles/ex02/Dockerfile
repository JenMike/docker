FROM ruby:latest

RUN apt-get update && apt-get -y install nodejs && gem install rails
RUN mkdir -p opt/app

ONBUILD WORKDIR /opt/app
ONBUILD ADD . /opt/app
ONBUILD EXPOSE 3000
ONBUILD RUN bundle update && bundle install && rails db:migrate && rails db:seed
