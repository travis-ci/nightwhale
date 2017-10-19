FROM centos:7

RUN yum groupinstall "Development Tools" -y
RUN yum install ruby ruby-devel -y
RUN gem install bundler --no-ri --no-rdoc
RUN gem install fpm --no-ri --no-rdoc
RUN gem install pleaserun --no-ri --no-rdoc
