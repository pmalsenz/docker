FROM ubuntu:16.04
MAINTAINER Peter Mueller "https://github.com/pmalsenz"

RUN apt-get update
RUN apt-get install -y ssh wget curl vim nano multitail moreutils nmap iftop htop ncftp bzip2 less lsof screen aptitude

RUN echo "deb http://packages.icinga.com/ubuntu icinga-xenial main" >/etc/apt/sources.list.d/icinga2.list
RUN echo "deb-src http://packages.icinga.com/ubuntu icinga-xenial main" >> /etc/apt/sources.list.d/icinga2.list
RUN wget -O - http://packages.icinga.com/icinga.key | apt-key add -
RUN apt-get update
RUN apt-get -y install icinga2 icingaweb2 

RUN mkdir /var/run/sshd
RUN echo 'root:root' |chpasswd
RUN sed -ri 's/^PermitRootLogin\s+.*/PermitRootLogin yes/' /etc/ssh/sshd_config
RUN sed -ri 's/UsePAM yes/#UsePAM yes/g' /etc/ssh/sshd_config

EXPOSE 22
EXPOSE 80
EXPOSE 5665

CMD ["/usr/sbin/sshd", "-D"]
