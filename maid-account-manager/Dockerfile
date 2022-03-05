FROM openjdk:8-jdk-slim

ENV APP_NAME maid-account-manager
ENV APP_FILE maid-account-manager-0.1.0.jar
ENV APP_HOME /usr/app

COPY . /var/tmp/$APP_NAME
WORKDIR /var/tmp/$APP_NAME
RUN ./mvnw install \
    && ./mvnw package \
    && mkdir -p $APP_HOME \
    && cp /var/tmp/$APP_NAME/target/$APP_FILE $APP_HOME \
    && rm -rf /var/tmp/$APP_NAME

WORKDIR $APP_HOME
ENTRYPOINT ["sh", "-c"]
CMD ["exec java -jar $APP_FILE"]
