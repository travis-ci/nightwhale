FROM ubuntu:18.04

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get -yq update
RUN apt-get -yq install software-properties-common
RUN add-apt-repository ppa:pdoes/ppa -y
RUN add-apt-repository ppa:brightbox/ruby-ng -y
RUN apt-get -yq update
RUN apt-get -yq install build-essential libncurses-dev git ruby ruby-dev rsync
RUN gem install bundler -v 2.3.27 --no-document
RUN gem install dotenv -v 2.8.1
RUN gem install fpm --no-document
RUN gem install pleaserun --no-document
