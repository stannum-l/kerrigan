FROM openjdk:8-jre

LABEL maintainer "Tin Lam <tin@irrational.io>"

# ENV VERSION=6.6.0.13
ENV VERSION=6.7.0.63

RUN curl -o /cmd.run.zip http://cdn.sencha.com/cmd/$VERSION/no-jre/SenchaCmd-$VERSION-linux-amd64.sh.zip \
  && unzip -p /cmd.run.zip > /cmd-install.run \
  && chmod +x /cmd-install.run \
  && /cmd-install.run -q -Dall=true -dir /opt/Sencha/Cmd/$VERSION \
  && install -dm777 -o root -g root /opt/Sencha/Cmd/repo \
  && rm /cmd-install.run /cmd.run.zip \
  && ln -s /opt/Sencha/Cmd/$VERSION/sencha /opt/Sencha/sencha \
  && apt-get update && apt-get install -y --no-install-recommends \
    ruby libffi6 python3 python3-pip python3-setuptools build-essential \
    ruby-dev libffi-dev \
  && pip3 install --upgrade pip \
  && gem update --system \
  && gem install compass \
  && apt-get remove -y ruby-dev build-essential libffi-dev \
  && apt-get autoremove -y \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/*

RUN pip3 --no-cache-dir install --upgrade awscli \
  && apt-get remove -y python3-pip python3-setuptools \
  && apt-get autoremove -y \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/*

ENTRYPOINT ["/opt/Sencha/sencha"]
