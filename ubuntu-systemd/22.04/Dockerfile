# Adapted from https://github.com/solita/docker-systemd
FROM ubuntu:22.04

# A workaround for Jammy issue with old, not updatable docker version for Xenial
RUN sed -i -e 's/^APT/# APT/' -e 's/^DPkg/# DPkg/' \
      /etc/apt/apt.conf.d/docker-clean
RUN apt update -yqq
RUN DEBIAN_FRONTEND=noninteractive apt-get install -yqq \
  --no-install-suggests --no-install-recommends apt-utils
RUN DEBIAN_FRONTEND=noninteractive apt-get install -yqq \
  --no-install-suggests --no-install-recommends systemd

# Don't start any optional services except for the few we need.
RUN find /etc/systemd/system \
         /lib/systemd/system \
         -path '*.wants/*' \
         -not -name '*journald*' \
         -not -name '*systemd-tmpfiles*' \
         -not -name '*systemd-user-sessions*' \
         -exec rm \{} \;

ENV container docker

RUN systemctl set-default multi-user.target

COPY container-setup /sbin/container-setup

CMD ["/bin/bash", "-c", "exec /sbin/init --log-target=journal 3>&1"]
