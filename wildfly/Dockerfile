FROM jboss/wildfly:18.0.1.Final
#RUN yum install -y xorg-x11-fonts-75dpi xorg-x11-fonts-Type1 openssl git-core fontconfig
RUN /opt/jboss/wildfly/bin/add-user.sh admin Admin#70365 --silent
EXPOSE 8080
EXPOSE 9990
EXPOSE 8787
RUN mkdir -p /opt/jboss/wildfly/modules/system/layers/base/com/mysql/main
COPY module.xml mysql-connector-java-8.0.19.jar /opt/jboss/wildfly/modules/system/layers/base/com/mysql/main/
COPY standalone.xml standalone-full.xml /opt/jboss/wildfly/standalone/configuration/
CMD ["/opt/jboss/wildfly/bin/standalone.sh", "-b", "0.0.0.0", "-bmanagement", "0.0.0.0", "-c", "standalone-full.xml", "--debug", "*:8787"]
