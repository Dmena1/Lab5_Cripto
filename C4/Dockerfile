FROM ubuntu:22.04

RUN apt-get update && apt-get install -y openssh-client openssh-server net-tools iputils-ping tcpdump

RUN useradd -rm -d /home/prueba -s /bin/bash -g root -G sudo -u 1000 prueba && \
    echo 'prueba:prueba' | chpasswd

RUN sed -i 's/#PermitRootLogin prohibit-password/PermitRootLogin yes/' /etc/ssh/sshd_config

RUN mkdir /var/run/sshd

EXPOSE 22
CMD ["/usr/sbin/sshd", "-D"]
