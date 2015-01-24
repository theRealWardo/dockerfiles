FROM ubuntu

MAINTAINER Matt Ward

RUN apt-get update
RUN apt-get install -y build-essential rubygems1.9.1 ruby1.9.1-dev

RUN gem install riemann-dash

EXPOSE 8000

# Share the config directory as a volume
VOLUME /etc/riemann-dash

ADD config.rb /etc/riemann-dash/config.rb

CMD riemann-dash /etc/riemann-dash/config.rb
