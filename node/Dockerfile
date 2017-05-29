FROM node:6.9.4

RUN apt-get update && apt-get install make ruby ruby-dev -y

RUN gem install sass compass

RUN curl -o- -L https://yarnpkg.com/install.sh | bash -s -- --version 0.23.2

RUN $HOME/.yarn/bin/yarn global add grunt-cli bower
