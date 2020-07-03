FROM ruby:2.7.1-buster
# Install yarn repository since Rails 6 depends on
# @see https://classic.yarnpkg.com/en/docs/install/#debian-stable
RUN curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add -
RUN echo "deb https://dl.yarnpkg.com/debian/ stable main" | tee /etc/apt/sources.list.d/yarn.list
# Install MySQL client repository
# @see https://linuxize.com/post/how-to-install-mysql-on-debian-10/
RUN wget -O /tmp/mysql-apt-config_0.8.13-1_all.deb http://repo.mysql.com/mysql-apt-config_0.8.13-1_all.deb \
 && apt update -qq \
 # Set noninteractive to suppress installation options of mysql-apt-config
 # @see https://stackoverflow.com/questions/7739645/install-mysql-on-ubuntu-without-a-password-prompt/7740393#7740393
 && DEBIAN_FRONTEND="noninteractive" apt install -y -q /tmp/mysql-apt-config_0.8.13-1_all.deb \
 && rm -f /tmp/mysql-apt-config_0.8.13-1_all.deb \
 && apt update -qq && apt install -y nodejs yarn mysql-client
RUN gem install bundle
RUN mkdir /workspace
WORKDIR /workspace

# Add a script to be executed every time the container starts.
COPY entrypoint.sh /usr/bin/entrypoint
RUN chmod +x /usr/bin/entrypoint
ENTRYPOINT ["entrypoint"]
EXPOSE 3000

# Start the main process.
CMD ["rails", "server", "--binding=0.0.0.0"]