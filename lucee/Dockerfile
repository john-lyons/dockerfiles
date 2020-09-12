FROM alpine:3.12
RUN apk --no-cache update
RUN apk --no-cache add openjdk11 curl

WORKDIR /opt/tomcat

RUN curl -o tomcat.tar.gz http://apache.mirrors.hoobly.com/tomcat/tomcat-9/v9.0.37/bin/apache-tomcat-9.0.37.tar.gz && \
tar -xvf tomcat.tar.gz && \
mv apache-tomcat-9.0.37/* /opt/tomcat/. && \
rm -rf /opt/tomcat/tomcat.tar.gz && \
rm -rf /opt/tomcat/webapps/* && \
cd /opt/tomcat/webapps && \
curl -o ROOT.war -L https://cdn.lucee.org/lucee-5.3.6.61.war


#ARG LUCEE_ADMIN_PASSWORD=
#ENV LUCEE_ADMIN_PASSWORD=${LUCEE_ADMIN_PASSWORD}

#RUN if [ "$LUCEE_ADMIN_PASSWORD" != "" ] ; then \
#WORKDIR /opt/tomcat/webapps/ROOT/lucee-server/context
#RUN echo "test" > /opt/tomcat/webapps/ROOT/lucee-server/context/password.txt
#    fi



EXPOSE 8080

CMD ["/opt/tomcat/bin/catalina.sh", "run"]
#WORKDIR
#RUN echo "test" > /opt/tomcat/webapps/ROOT/WEB-INF/lucee-server/context/password.txt