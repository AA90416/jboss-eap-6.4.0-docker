FROM jboss/base-jdk:8

MAINTAINER Rob

COPY   jboss-eap-6.4.0.zip /tmp/

USER root 


RUN yum install -y unzip \
    && unzip /tmp/jboss-eap-6.4.0.zip -d /opt/rh \
    && export EAP_HOME=/opt/rh/jboss-eap-6.4 \
    && /opt/rh/jboss-eap-6.4/bin/add-user.sh admin Snet.1234TECH --silent


EXPOSE 8089 9990 9999


WORKDIR  /opt/rh/jboss-eap-6.4/bin

ENTRYPOINT ["./standalone.sh", "-b", "0.0.0.0", "-bmanagement", "0.0.0.0"]
