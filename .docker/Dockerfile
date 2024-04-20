FROM eclipse-temurin:17-alpine

RUN addgroup -g 1028 devopsc \
    && adduser -D -G devopsc admin

VOLUME /tmp

ARG JAR_FILE
ARG ARG DB_PASWWORD
COPY ${JAR_FILE} /tmp/app.jar

ENV DB_PASWWORD=$DB_PASWWORD

RUN chown -R admin:devopsc /tmp

USER admin

ENTRYPOINT [ "java","-jar","/app.jar" ]