## docker build -t ft-rails:on-build .
## make an app cause uhhhh, not my job.... but like a simple hello world should be fine. i just dont know how to make one right now
## launches into irb -- interactive ruby
## docker run -it --rm -p 3000:3000 ft-rails:on-build
## or ya know, use the other dockerfile like the instructions suggest and be a cool kid. by using both files. but like not me lmao
FROM ruby

LABEL maintainer="saolivei@student.42.us.org"

RUN apt-get update -y; apt-get install -y build-essential libpq-dev nodejs sqlite3

ONBUILD COPY app /opt/app
ONBUILD WORKDIR /opt/app

ONBUILD RUN bundle install
ONBUILD RUN rake db:migrate
ONBUILD RUN rake db:seed

ONBUILD EXPOSE 3000

# put in new dockerfile and run it cause it be like that somtime
# FROM ft-rails:on-build
# EXPOSE 3000
# CMD ["rails", "s", "-b", "0.0.0.0", "-p", "3000"]
