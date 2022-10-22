FROM alpine:3.14
RUN apk update && apk add maven git
WORKDIR /tmp
RUN git clone https://github.com/shephertz/App42PaaS-Java-MySQL-Sample.git
RUN mvn package -f App42PaaS*/