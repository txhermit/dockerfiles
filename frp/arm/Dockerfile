#
# Dockerfile for frp-arm
#

FROM alpine:3
MAINTAINER EasyPi Software Foundation

ARG FRP_VERSION=0.45.0
ARG FRP_FILE=frp_${FRP_VERSION}_linux_arm.tar.gz
ARG FRP_URL=https://github.com/fatedier/frp/releases/download/v${FRP_VERSION}/${FRP_FILE}

WORKDIR /opt/frp

RUN set -xe \
    && apk add --no-cache curl tar \
    && curl -sSL $FRP_URL | tar xz --strip 1 \
    && apk del curl tar

EXPOSE 7000/tcp 7000/udp 7500/tcp

CMD ["./frps", "-c", "frps.ini"]
