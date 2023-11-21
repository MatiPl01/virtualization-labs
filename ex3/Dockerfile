FROM centos:7
LABEL "maintainer"="Mateusz Łopaciński"
RUN yum -y install httpd && yum clean all && rm -rf /var/cache/yum
COPY index.html /var/www/html
EXPOSE 80
CMD ["httpd", "-D", "FOREGROUND"]

# docker build -t laborki .
# docker start laborki
