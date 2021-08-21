FROM ruby:2.7.2

# Rails6 からは以下のインストールが必要
# https://yarnpkg.com/lang/en/docs/install/#debian-stable
RUN curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add - && \
  echo "deb https://dl.yarnpkg.com/debian/ stable main" | tee /etc/apt/sources.list.d/yarn.list && \
  apt-get update -qq && apt-get install -y nodejs postgresql-client vim && \
  apt-get install -y yarn && \
  apt-get install -y imagemagick && \
  apt-get install -y libvips-tools && \
  apt-get install -y locales

RUN curl -sL https://deb.nodesource.com/setup_7.x | bash - && \
    apt-get install nodejs

RUN mkdir /rails-react-docker
WORKDIR /rails-react-docker
COPY Gemfile /rails-react-docker/Gemfile
COPY Gemfile.lock /rails-react-docker/Gemfile.lock
RUN bundle install
COPY . /rails-react-docker

COPY entrypoint.sh /usr/bin/
RUN chmod +x /usr/bin/entrypoint.sh
ENTRYPOINT ["entrypoint.sh"]
EXPOSE 3000

CMD ["rails", "server", "-b", "0.0.0.0"]