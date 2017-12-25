FROM kolla/ubuntu-source-barbican-api:3.0.3
MAINTAINER Tin Lam <tin@irrational.io>
USER root
RUN apt-get update; \
    apt-get upgrade -y; \
    apt-get install -y --no-install-recommends \
        pki-base \
    apt-get clean -y; \
    rm -rf \
        /root/.cache \
        /var/lib/apt/lists/*
USER barbican
