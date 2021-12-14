FROM centos:latest

# Change the default user in future: Done to avoid conflicts in bounty submissions file paths
WORKDIR /root

RUN yum update -y && yum install -y git; cd /root && git clone https://github.com/ranmses/gc-b71 