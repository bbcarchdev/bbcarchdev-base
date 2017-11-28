## Base image for BBC Archive Development containers
##
## This image is based upon a standard Debian image, but adds the keys and APT
## repositories that we use.
##
## https://github.com/bbcarchdev/bbcarchdev-base

FROM bbcarchdev/bbcarchdev-base:live

## Add the BBC Archive Development APT source for the staging environment
RUN echo "deb [arch=amd64] https://apt.bbcarchdev.net/debian wheezy stage" | tee -a /etc/apt/sources.list && \
	apt-get update -qq
