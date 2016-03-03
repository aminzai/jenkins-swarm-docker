FROM ubuntu:14.04

ENV JENKINS_SWARM_VERSION 2.0

# Install and configure a basic SSH server
RUN \
 sed -i 's/archive.ubuntu.com/free.nchc.org.tw/g' /etc/apt/sources.list && \
 apt-get update && \
 apt-get install -y \
 openssh-server \
 supervisor \
 curl \
 openjdk-7-jdk && \
 apt-get clean -y && \
 rm -rf /var/lib/apt/lists/*

COPY swarm-client-2.0-jar-with-dependencies.jar /usr/share/jenkins/
RUN chmod 755 /usr/share/jenkins

CMD ["/usr/bin/java", "-jar", "/usr/share/jenkins/swarm-client-2.0-jar-with-dependencies.jar"]
