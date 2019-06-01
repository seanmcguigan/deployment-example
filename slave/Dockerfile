FROM jenkins/slave

USER root

# Install docker
ENV DOCKER_VERSION 18.09.6  

RUN set -x \
  && curl -fSL "https://download.docker.com/linux/static/stable/x86_64/docker-${DOCKER_VERSION}.tgz" -o docker.tgz \
  && tar -xzvf docker.tgz \
  && mv docker/* /usr/local/bin/ \
  && rmdir docker \
  && rm docker.tgz \
  && docker -v
RUN groupadd docker
RUN usermod -aG docker jenkins
USER jenkins
