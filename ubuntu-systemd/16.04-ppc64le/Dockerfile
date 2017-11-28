# Adapted from https://github.com/solita/docker-systemd
FROM ppc64le/ubuntu:16.04

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
