FROM ubuntu
MAINTAINER Daichi TOMA <amothic@gmail.com>

RUN apt-get update
RUN apt-get upgrade -y

# Install mumble-server
RUN apt-get install -y mumble-server

# Install superviser
RUN apt-get install -y supervisor
RUN mkdir -p /var/log/supervisor
RUN locale-gen en_US en_US.UTF-8
ADD supervisord.conf /etc/supervisor/conf.d/supervisord.conf

RUN /usr/sbin/murmurd -fg -ini /etc/mumble-server.ini -supw admin
EXPOSE 64738

CMD ["/usr/bin/supervisord"]
