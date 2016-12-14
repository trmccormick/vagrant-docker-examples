FROM ruby:2.3

# see update.sh for why all "apt-get install"s have to stay as one long line
RUN apt-get update && apt-get install -y nodejs --no-install-recommends && rm -rf /var/lib/apt/lists/*

# see http://guides.rubyonrails.org/command_line.html#rails-dbconsole
RUN apt-get update && apt-get install -y mysql-client postgresql-client sqlite3 --no-install-recommends && rm -rf /var/lib/apt/lists/*

ENV RAILS_VERSION 5.0.0.1

RUN gem install rails --version "$RAILS_VERSION"

FROM rails
MAINTAINER Laura Frank <laura@codeship.com>
RUN mkdir -p /var/app
COPY ./example-rails-app /var/app
WORKDIR /var/app
RUN bundle install
CMD rails s -b 0.0.0.0
