FROM maven:3-jdk-8-alpine

ADD https://github.com/ufoscout/docker-compose-wait/releases/download/2.2.1/wait /wait
RUN chmod +x /wait

ADD . /code
WORKDIR /code

RUN mvn package

ENV SERVER_SSL_KEYSTORE file:/code/library.p12
ENV SERVER_SSL_KEYSTORETYPE PKCS12
ENV SERVER_SSL_KEYSTOREPASSWORD 1mSmz7gN6SVHi
ENV SERVER_SSL_KEYALIAS library
ENV SECURITY_REQUIRESSL true

CMD /wait && java -jar target/gateway.jar