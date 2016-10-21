FROM ubuntu
MAINTAINER Blubber:Henri

WORKDIR /opt
RUN apt-get update
RUN apt-get install -y wget
RUN wget https://sonatype-download.global.ssl.fastly.net/nexus/3/nexus-3.0.2-02-unix.tar.gz
RUN apt-get install -y default-jre
RUN tar -zxvf nexus-3.0.2-02-unix.tar.gz
EXPOSE 8081
ENTRYPOINT /opt/nexus-3.0.2-02/bin/nexus start && bash
