FROM alpine:3.14
RUN apk update && apk add maven git
ENV CONF=App42PaaS-Java-MySQL-Sample/WebContent/Config.properties
WORKDIR /tmp
RUN git clone https://github.com/shephertz/App42PaaS-Java-MySQL-Sample.git
RUN echo "app42.paas.db.username = $USER\n" > ${CONF}
RUN echo "app42.paas.db.port = $PORT\n\" >> ${CONF}
RUN echo "app42.paas.db.password = $PASS\n\" >> ${CONF}
RUN echo "app42.paas.db.ip = $DBIP\n\" >> ${CONF}
RUN echo "app42.paas.db.name = $DBNAME\n" >> ${CONF}
RUN mvn package -f App42PaaS*/