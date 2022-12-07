ARG ALPINE_VERSION=3.13
ARG AWS_CDK_VERSION=2.45.0
ARG IMAGE_NAME ?= contino/aws-cdk:$(AWS_CDK_VERSION)

FROM alpine:${ALPINE_VERSION}

RUN apk -v --no-cache --update add \
        nodejs \
		projen \
        npm \
        groff \
        less \
        bash \
        make \
        curl \
        wget \
        zip \
        git \
        && \
    npm install -g aws-cdk@${AWS_CDK_VERSION}

VOLUME [ "/root/.aws" ]
VOLUME [ "/opt/app" ]

WORKDIR /opt/app

CMD ["cdk", "--version"]
