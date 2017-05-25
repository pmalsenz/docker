FROM ubuntu:16.04
MAINTAINER Peter Mueller "https://github.com/pmalsenz"

RUN apt-get update
RUN apt-get install -y ssh wget curl vim nano multitail moreutils nmap iftop htop ncftp bzip2 less lsof screen aptitude

RUN mkdir /var/run/sshd
RUN echo 'root:root' |chpasswd
RUN sed -ri 's/^PermitRootLogin\s+.*/PermitRootLogin yes/' /etc/ssh/sshd_config
RUN sed -ri 's/UsePAM yes/#UsePAM yes/g' /etc/ssh/sshd_config

RUN curl -sSL https://install.pi-hole.net | bash

EXPOSE 22
EXPOSE 53
EXPOSE 53/udp
EXPOSE 80

CMD ["/usr/sbin/sshd", "-D"]
