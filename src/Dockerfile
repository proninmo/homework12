FROM maven:3-eclipse-temurin-11-alpine
RUN apk update && apk add maven git
WORKDIR /tmp
RUN git clone https://github.com/shephertz/App42PaaS-Java-MySQL-Sample.git
COPY Config.properties /tmp/App42PaaS-Java-MySQL-Sample/WebContent/
WORKDIR /tmp/App42PaaS-Java-MySQL-Sample
RUN mvn clean package
WORKDIR /tmp/war
RUN mv /tmp/App42PaaS-Java-MySQL-Sample/target/*.war /tmp/war
RUN rm -rf /tmp/App42PaaS-Java-MySQL-Sample