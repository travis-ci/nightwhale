FROM travisci/ubuntu-systemd:18.04-ppc64le

ENV DEBIAN_FRONTEND noninteractive

ADD packages.txt /var/tmp/packages.txt

RUN apt-get update -yq && apt-get install -y software-properties-common

RUN apt-add-repository -y multiverse && \
    apt-add-repository -y restricted && \
    apt-add-repository -y universe

RUN apt-get update -yq && \
    cat /var/tmp/packages.txt \
      | xargs apt-get install -yq --no-install-suggests --no-install-recommends
