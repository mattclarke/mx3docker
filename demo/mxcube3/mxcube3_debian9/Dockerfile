##############################################################################
# Dockerfile to run MXCuBE web server
##############################################################################

FROM debian:9
MAINTAINER Marcus Oscarsson <marcus.oscarsson@esrf.fr>

ENV TERM linux

# Install system pacakges

RUN apt-get update && apt-get -y upgrade && \
    apt-get install -y apt-utils curl git sudo build-essential wget python

WORKDIR /opt

# Install MXCuBE3
COPY debian-install.sh /opt/debian-install.sh
RUN cd /opt && chmod +x debian-install.sh && ./debian-install.sh

COPY mxcube /usr/local/bin/
COPY docker-entrypoint.sh /usr/local/bin/
ENTRYPOINT ["/usr/local/bin/docker-entrypoint.sh"]

EXPOSE 8090 8081