FROM ubuntu:14.04
MAINTAINER Blubber:Henri

# Instructions from https://vexxhost.com/resources/tutorials/how-to-install-configure-and-use-jenkins-on-ubuntu-14.04/

RUN apt-get update
RUN apt-get install -y openjdk-7-jdk
RUN apt-get install -y wget
RUN wget -q -O - https://jenkins-ci.org/debian/jenkins-ci.org.key | apt-key add -
RUN sh -c 'echo deb http://pkg.jenkins-ci.org/debian binary/ > /etc/apt/sources.list.d/jenkins.list'
RUN apt-get update
RUN apt-get install -y jenkins
EXPOSE 8080
ENTRYPOINT service jenkins start && bash


