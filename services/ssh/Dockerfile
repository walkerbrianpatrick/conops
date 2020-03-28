FROM ubuntu:bionic-20200311

RUN apt-get update;\
        apt-get install -y --no-install-recommends \
        iproute2 \
        iputils-ping \
	ssh \
	openssh-server

RUN mkdir /run/sshd
RUN mkdir -p /root/.ssh
COPY src/resources/authorized_keys /root/.ssh/authorized_keys

EXPOSE 22
CMD ["/usr/sbin/sshd", "-D"]
