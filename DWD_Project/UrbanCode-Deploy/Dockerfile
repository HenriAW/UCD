FROM ubuntu:14.04
MAINTAINER Blubber:Henri

RUN apt-get update
RUN apt-get install -y wget

#IBM Urbancode Deploy 6.2.2 Multiplatform English Trial
RUN wget https://www15.software.ibm.com/sdfdl/v2/fulfill/CNEM5EN/Xa.2/Xb.aFmQQe8PD7-qs_QgISswLvmRHiuKk1ld2vyskqTJSmw/Xc.CNEM5EN/URBANCODE_DEPLOY_6.2.2_EN_EVAL.zip/Xd./Xf.LPR.F1AZ/Xg.8840890/Xi.RATLe-UCDeploy-EVAL/XY.regsrvs/XZ.i05QH2rmTG2qr3nK7Y4UhNh0WOw/URBANCODE_DEPLOY_6.2.2_EN_EVAL.zip
RUN DEBIAN_FRONTEND=noninteractive apt-get install -y  openjdk-7-jdk mysql-server libmysql-java
RUN service mysql start\
&& mysql -u root -e "create database uDeploy;"\
&& mysql -u root -e "create user 'udeploy'@'localhost' identified by '';"\
&& mysql -u root -e "grant all on uDeploy.* to 'udeploy'@'localhost' with grant option;"
RUN apt-get install -y unzip default.jre
RUN unzip URBANCODE_DEPLOY_6.2.2_EN_EVAL.zip

#ENV JAVA_HOME="/usr/lib/jvm/java-7-openjdk-amd64"
ENV JAVA_HOME="/usr/"

#Test ***************************************************
COPY install.extra.properties /ibm-ucd-install/
WORKDIR /ibm-ucd-install/
RUN cat install.extra.properties >> install.properties &&\
sed -i '/chmod +x "opt\/apache-ant-\${OUR_ANT_VERSION}\/bin\/ant"/ s/$/; sync/' install-server.sh && \
chmod +x install-server.sh; sync
