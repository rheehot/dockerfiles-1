#
# docker run \
#   $(env | grep OS_ | sed 's/OS_/ -e OS_/g' | tr -d '\n') \
#   --rm \
#   leoh0/openstack-client \
#   "$@"
#

FROM alpine:latest

MAINTAINER Eohyung Lee <liquidnuker@gmail.com>

# Alpine-based installation
# #########################
RUN apk add --update \
  python-dev \
  py-pip \
  py-setuptools \
  ca-certificates \
  gcc \
  libffi-dev \
  openssl-dev \
  musl-dev \
  linux-headers \
  && pip install --upgrade --no-cache-dir \
     pip \
     setuptools \
     python-openstackclient \
     python-designateclient \
  && apk del gcc musl-dev linux-headers libffi-dev \
  && rm -rf /var/cache/apk/*

ENTRYPOINT ["/usr/bin/openstack"]
