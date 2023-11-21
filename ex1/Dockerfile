FROM centos:7
LABEL "maintainer"="Mateusz Łopaciński"
RUN yum -y install httpd && yum clean all && rm -rf /var/cache/yum
EXPOSE 80

# Path: ex1/commands
# docker build -t laborki .
# docker run -ti --name laborki -p 80:80 laborki /bin/bash
# docker run -d --name laborki -p 80:80 laborki
# docker ps
# docker images
