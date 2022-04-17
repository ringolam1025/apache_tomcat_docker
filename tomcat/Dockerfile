FROM ubuntu

RUN apt-get update && \
      apt-get -y install sudo openjdk-8-jre vim
RUN adduser --disabled-password --gecos '' web
RUN adduser web sudo
RUN echo '%sudo ALL=(ALL) NOPASSWD:ALL' >> /etc/sudoers
USER web

WORKDIR /home/web

ADD apache-tomcat-8.5.57.tar.gz .

RUN sudo chown -R web:web apache-tomcat-8.5.57
RUN sudo chmod -R 755 apache-tomcat-8.5.57

RUN mkdir scstac
RUN mkdir tmp

CMD ["apache-tomcat-8.5.57/bin/catalina.sh", "run"]