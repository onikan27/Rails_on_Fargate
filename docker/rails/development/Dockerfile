FROM ruby:2.6.3
RUN apt-get update -qq && \
    apt-get install -y build-essential \ 
                       libpq-dev \        
                       nodejs           

RUN mkdir /app
WORKDIR /app
COPY Gemfile /app/Gemfile
COPY Gemfile.lock /app/Gemfile.lock
RUN gem install bundler
RUN bundle install
ADD . /app
EXPOSE 3000

CMD ["/bin/sh", "-c", "bundle exec rails s -p 3000 -b 0.0.0.0"]
