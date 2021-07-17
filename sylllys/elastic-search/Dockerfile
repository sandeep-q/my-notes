FROM elasticsearch:7.10.1

USER root

RUN yum install sudo -y
RUN sudo yum -y install openssh-server openssh-clients
RUN sudo systemctl enable sshd


ENV discovery.type=single-node

ADD . /elastic-search/
WORKDIR /elastic-search/

RUN mv /elastic-search/startupForDockerContainer /bin/
RUN chmod 777 /bin/startupForDockerContainer



CMD ["/bin/startupForDockerContainer"]