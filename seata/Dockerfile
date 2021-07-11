ARG SEATA_VERSION
FROM seataio/seata-server:${SEATA_VERSION}

RUN rm -f /seata-server/libs/mysql-connector-java-5.1.35.jar
RUN cp -f /seata-server/libs/jdbc/mysql-connector-java-8.0.19.jar /seata-server/libs/mysql-connector-java-8.0.19.jar
