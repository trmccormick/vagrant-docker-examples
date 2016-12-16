FROM ruby:2.3.3

RUN apt-get update -qq && apt-get install -y build-essential libpq-dev nodejs
RUN apt-get update
RUN apt-get install -y mysql-client

RUN mkdir /myapp
WORKDIR /myapp
ADD ./example-rails-app/Gemfile /myapp/Gemfile
ADD ./example-rails-app/Gemfile.lock /myapp/Gemfile.lock
RUN bundle install
COPY ./example-rails-app /myapp
CMD rails s -b 0.0.0.0
