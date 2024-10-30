FROM travisci/ubuntu-systemd:22.04

ENV DEBIAN_FRONTEND noninteractive

ADD packages.txt /var/tmp/packages.txt

# Disable the problematic post-invoke script
# RUN echo 'APT::Update::Post-Invoke-Success { "true"; };' > /etc/apt/apt.conf.d/no-cache-update

RUN apt-get update -yq && apt-get install -y software-properties-common

RUN apt-add-repository -y multiverse && \
    apt-add-repository -y restricted && \
    apt-add-repository -y universe

RUN apt-get update -yq && \
    cat /var/tmp/packages.txt \
      | xargs apt-get install -yq --no-install-suggests --no-install-recommends

RUN apt-get clean && rm -rf /var/lib/apt/lists/*
