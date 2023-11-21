FROM centos:7
LABEL "maintainer"="Mateusz Łopaciński"
RUN yum -y install httpd && yum clean all && rm -rf /var/cache/yum
EXPOSE 80
CMD ["httpd", "-D", "FOREGROUND"]

# docker build -t laborki .

# docker run -d --name laborki -p 80:80 laborki
# docker ps

# docker exec -ti laborki /bin/bash
# ps aux | grep httpd
# curl localhost
