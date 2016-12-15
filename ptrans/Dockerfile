FROM openjdk:jre-alpine

RUN apk add --update netcat-openbsd && rm -rf /var/cache/apk/*
ARG PTRANS_VERSION=0.21.0
ADD https://github.com/hawkular/hawkular-metrics/releases/download/${PTRANS_VERSION}/ptrans-${PTRANS_VERSION}.Final-dist.zip /tmp/
WORKDIR /opt/app/ptrans-${PTRANS_VERSION}.Final
RUN unzip /tmp/ptrans-${PTRANS_VERSION}.Final-dist.zip -d /opt/app/ \
 && rm /tmp/*.zip

USER 1001
ENTRYPOINT ["java", "-jar", "ptrans-all.jar", "-c" ]
CMD ["ptrans.conf"]
