FROM ubuntu:16.04

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get -yq update
RUN apt-get -yq install software-properties-common
RUN add-apt-repository ppa:pdoes/ppa -y
RUN add-apt-repository ppa:brightbox/ruby-ng -y
RUN apt-get -yq update
RUN apt-get -yq install build-essential libncurses-dev git ruby2.4 libruby2.4 ruby2.4-dev rsync
RUN gem install bundler --no-ri --no-rdoc
RUN gem install fpm --no-ri --no-rdoc
RUN gem install pleaserun --no-ri --no-rdo
