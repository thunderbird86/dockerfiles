FROM openjdk:14-alpine
LABEL mainteiner="anton_vasilchenko https://github.com/thunderbird86" \
      description="CMAK pka Kafka-manager"

ENV CMAK_VERSION 3.0.0.5

RUN cd /opt \
    && wget "https://github.com/yahoo/CMAK/releases/download/${CMAK_VERSION}/cmak-${CMAK_VERSION}.zip" \
    && apk update && apk add bash curl \
    && unzip cmak-${CMAK_VERSION}.zip \
    && mv cmak-${CMAK_VERSION} /opt/cmak

WORKDIR /opt/cmak

EXPOSE 9000
ENTRYPOINT ["./bin/cmak","-Dconfig.file=conf/application.conf"]
