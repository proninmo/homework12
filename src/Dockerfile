FROM alpine:3.14
RUN apk update && apk add maven git
ENV CONF=App42PaaS-Java-MySQL-Sample/WebContent/Config.properties
ENV MYSQL_USER: 'user'
ENV MYSQL_DATABASE: 'homework12'
ENV MYSQL_PASSWORD: 'User123qaz456wsx'
ENV DBIP: 'db'
ENV PORT: '3306' 
WORKDIR /tmp
RUN git clone https://github.com/shephertz/App42PaaS-Java-MySQL-Sample.git
RUN echo "app42.paas.db.username = $MYSQL_USER\n" > ${CONF}
RUN echo "app42.paas.db.port = $PORT\n" >> ${CONF}
RUN echo "app42.paas.db.password = $MYSQL_PASSWORD\n" >> ${CONF}
RUN echo "app42.paas.db.ip = $DBIP\n" >> ${CONF}
RUN echo "app42.paas.db.name = $MYSQL_DATABASE\n" >> ${CONF}
RUN mvn package -f App42PaaS-Java-MySQL-Sample/ 
WORKDIR /tmp/war 
RUN mv /tmp/App42PaaS-Java-MySQL-Sample/target/*.war /tmp/war
RUN rm -rf /tmp/App42PaaS-Java-MySQL-Sample