FROM ruby:latest
MAINTAINER lagagain

# install node.js
WORKDIR "/root"
RUN mkdir nodejs
RUN curl -O "https://nodejs.org/dist/v12.18.3/node-v12.18.3-linux-x64.tar.xz"
RUN tar -xf node-v12.18.3-linux-x64.tar.xz
RUN mv node-v12.18.3-linux-x64/* ./nodejs
RUN rm -rf node-v12.18.3-linux-x64.tar.xz node-v12.18.3-linux-x64
ENV PATH $PATH:/root/nodejs/bin/
RUN npm i -g yarn

# install radils
RUN gem install rails

# build App
WORKDIR "/usr/src/app"
CMD ["rails", "server", "-b", "0.0.0.0"]

