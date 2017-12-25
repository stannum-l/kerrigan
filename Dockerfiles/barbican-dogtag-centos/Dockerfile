FROM kolla/centos-source-barbican-api:3.0.3
MAINTAINER Tin Lam <tin@irrational.io>
USER root
RUN yum install -y pki base; \
    yum clean all
USER barbican
