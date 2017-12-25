FROM gcr.io/google_containers/ubuntu-slim:0.14
MAINTAINER Tin Lam <tin@irrational.io>
ENV DEBIAN_FRONTEND noninteractive

COPY assets/ /opt/k8swebhook

RUN set -xe; \
    apt-get update; \
    apt-get upgrade -y; \
    apt-get clean -y; \
    mv /opt/k8swebhook/k8s-keystone-auth /usr/local/bin; \
    rm -rf \
        /root/.cache \
        /var/lib/apt/lists/*

EXPOSE 8443
VOLUME ["/tmp", "/run"]
ENTRYPOINT ["/opt/k8swebhook/entrypoint.sh"]
