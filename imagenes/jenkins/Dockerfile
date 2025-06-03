FROM jenkins/jenkins:lts

USER root
RUN apt-get update && apt-get install -y maven \
    && [ ! -f /usr/bin/mvn ] && ln -s /usr/share/maven/bin/mvn /usr/bin/mvn || echo "Mvn already exists"

USER jenkins