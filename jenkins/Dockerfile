FROM jenkins/jenkins:lts-jdk21

USER root

RUN apt-get update && \
    apt-get install -y \
        docker.io \
        docker-buildx-plugin \
        docker-compose-plugin && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

USER jenkins
