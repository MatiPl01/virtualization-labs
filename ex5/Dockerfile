FROM centos:7
RUN yum -y install sudo openssl
RUN echo 'root:DockerLab' | chpasswd
RUN groupadd sudo
RUN useradd -m -p $(openssl passwd -1 DockerLab) jan && \
    useradd -m -p $(openssl passwd -1 DockerLab) kinga
RUN usermod -aG users,sudo jan && \
    usermod -aG users,sudo kinga && \
    echo "%wheel ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers && \
    echo "%sudo ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers
CMD ["tail", "-f", "/dev/null"]

# docker stop laborki && docker rm laborki && docker build -t laborki . && docker run -dit --name laborki -p 80:80 laborki

# docker exec -it laborki bash -c "sudo -u jan whoami"
# docker exec -it laborki bash -c "groups jan"

# docker exec -it laborki bash -c "sudo -u kinga whoami"
# docker exec -it laborki bash -c "groups kinga"
