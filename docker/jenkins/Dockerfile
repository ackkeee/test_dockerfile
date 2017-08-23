FROM centos:latest

# Install for packages
# 1. system update
# 2. install java
# 3. set local time
# 4. install jenkins

RUN yum -y update \
  && yum clean all \
  && yum install -y epel-release java-1.8.0-openjdk java-1.7.0-openjdk-devel ntp sshpass wget initscripts \
  && unlink /etc/localtime \
  && ln -s /usr/share/zoneinfo/Japan /etc/localtime \
  && wget -O /etc/yum.repos.d/jenkins.repo http://pkg.jenkins-ci.org/redhat-stable/jenkins.repo \
  && rpm --import https://jenkins-ci.org/redhat/jenkins-ci.org.key \
  && yum install -y jenkins

EXPOSE 8080
CMD systemctl start jenkins.service \
  && yum clean all \
  && sleep 5 \
  && tail -f /var/log/jenkins/jenkins.log

