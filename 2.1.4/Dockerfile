FROM ubuntu:14.04

MAINTAINER Tom Cowling <tcowling@cellusys.com>

RUN apt-get update -yqq
RUN apt-get install -yqq wget
RUN apt-get -yqq install build-essential zlib1g-dev libssl-dev libreadline6-dev libyaml-dev
RUN wget http://cache.ruby-lang.org/pub/ruby/2.1/ruby-2.1.4.tar.gz --output-document=/tmp/ruby-2.1.4.tar.gz
RUN mkdir -p /opt/ruby
RUN tar xzvf /tmp/ruby-2.1.4.tar.gz -C /opt/ruby --strip-components=1
WORKDIR /opt/ruby
RUN ./configure
RUN make
RUN make install
RUN rm -rf /tmp/ruby-2.1.4.tar.gz
RUN rm -rf /opt/ruby
RUN gem install bundler
