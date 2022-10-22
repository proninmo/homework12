FROM alpine:3.14
RUN apk update && apk add maven git
WORKDIR /tmp
RUN git clone https://github.com/shephertz/App42PaaS-Java-MySQL-Sample.git
RUN echo "app42.paas.db.username = $USER\n" > App42PaaS-Java-MySQL-Sample/WebContent/Config.properties
RUN echo "app42.paas.db.port = $PORT\n\" >> App42PaaS-Java-MySQL-Sample/WebContent/Config.properties
RUN echo "app42.paas.db.password = $PASS\n\" >> App42PaaS-Java-MySQL-Sample/WebContent/Config.properties
RUN echo "app42.paas.db.ip = $DBIP\n\" >> App42PaaS-Java-MySQL-Sample/WebContent/Config.properties
RUN echo "app42.paas.db.name = $DBNAME\n" >> App42PaaS-Java-MySQL-Sample/WebContent/Config.properties
RUN mvn package -f App42PaaS*/