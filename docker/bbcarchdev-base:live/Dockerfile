## Base image for BBC Archive Development containers
##
## This image is based upon a standard Debian image, but adds the keys and APT
## repositories that we use.
##
## https://github.com/bbcarchdev/bbcarchdev-base

FROM debian:wheezy-backports

ENV DEBIAN_FRONTEND=noninteractive
ENV LANG=C

# Prerequisites
RUN apt-get update -qq && \
	apt-get install -y --no-install-recommends apt-transport-https curl ca-certificates
	
# Fetch and install the ISRG Root certificate
RUN curl https://letsencrypt.org/certs/isrgrootx1.pem.txt | tee /usr/share/ca-certificates/isrgrootx1.crt && \
	echo "isrgrootx1.crt" | tee -a /etc/ca-caertificates.conf

# Fetch and install the Let's Encrypt CA certificate
RUN curl https://letsencrypt.org/certs/lets-encrypt-x3-cross-signed.pem.txt | tee /usr/share/ca-certificates/lets-encrypt-x3-cross-signed.crt && \
	echo "lets-encrypt-x3-cross-signed.crt" | tee -a /etc/ca-certificates.conf

# Ensure applications use the newly-added certificates
RUN update-ca-certificates

# Install the BBC Archive Development APT key
RUN curl https://raw.githubusercontent.com/bbcarchdev/bbcarchdev-keys/main/bbcarchdev-apt.asc | apt-key add -

## Add the BBC Archive Development APT source
RUN echo "deb [arch=amd64] https://apt.bbcarchdev.net/debian wheezy main ports live" | tee -a /etc/apt/sources.list

# Install bbcarchdev-base
RUN apt-get update -qq && \
	apt-get install -y --no-install-recommends bbcarchdev-base
