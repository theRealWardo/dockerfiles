FROM ubuntu

MAINTAINER Matt Ward

RUN apt-get update
RUN apt-get install -y curl openjdk-7-jre-headless

RUN curl https://aphyr.com/riemann/riemann_0.2.6_all.deb > /tmp/riemann_0.2.6_all.deb
RUN dpkg -i /tmp/riemann_0.2.6_all.deb

# Events
EXPOSE 5555
EXPOSE 5555/udp

# Websocket
EXPOSE 5556

# Share the config directory as a volume
VOLUME /etc/riemann

ADD riemann.config /etc/riemann/riemann.config

CMD riemann /etc/riemann/riemann.config
