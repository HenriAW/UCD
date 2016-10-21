FROM ubuntu:14.04
MAINTAINER Blubber:Henri

WORKDIR /opt
RUN apt-get update
RUN apt-get install -y wget
RUN wget https://www.atlassian.com/software/jira/downloads/binary/atlassian-jira-software-7.2.3-x64.bin
RUN chmod a+x atlassian-jira-software-7.2.3-x64.bin
ADD ./response.varfile /opt/
RUN ./atlassian-jira-software-7.2.3-x64.bin -q -varfile response.varfile
EXPOSE 8080
ENTRYPOINT service jira start && bash

