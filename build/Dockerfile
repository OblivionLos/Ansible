# Base image of Ubuntu
FROM ubuntu:18.04
#Prepare for Ansible
RUN apt-get update && apt-get install -y python3 \
    python3-pip
RUN apt-get install -y openssh-server
RUN service ssh start

# Add new user
RUN useradd -s /bin/bash -d /home/d1masik -m d1masik
RUN passwd -d d1masik
# Change user
# Add ssh-key
COPY id_rsa.pub /home/d1masik/.ssh/authorized_keys
COPY id_rsa.pub ~/.ssh/authorized_keys
# Increase lifetime
EXPOSE 22
CMD ["/usr/sbin/sshd", "-D"]
#ENTRYPOINT ["tail", "-f", "/dev/null"]
