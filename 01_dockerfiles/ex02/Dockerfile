FROM ruby
RUN apt-get update -y && apt-get install build-essential -y && apt-get install sqlite3 -y && apt-get install nodejs -y && gem install bundler
RUN mkdir /opt/app
WORKDIR /opt/app
RUN gem install rails
ONBUILD COPY . /opt/app
ONBUILD RUN bundle install
ONBUILD RUN rake db:migrate && rake db:seed
ONBUILD EXPOSE 3000
