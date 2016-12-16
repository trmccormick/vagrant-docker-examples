FROM ruby:2.3.3

# run update
RUN apt-get update -qq
RUN apt-get install -y build-essential libpq-dev nodejs

# install mysql-client
RUN apt-get install -y mysql-client

# RUN apt-get update

RUN mkdir /myapp
VOLUME ["/myapp"]

WORKDIR /myapp

ADD ./example-rails-app/Gemfile /myapp/Gemfile
ADD ./example-rails-app/Gemfile.lock /myapp/Gemfile.lock
RUN bundle install

# ADD ./example-rails-app /myapp
CMD rails s -b 0.0.0.0
