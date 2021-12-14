FROM amazonlinux:2
# Change the default user in future: Done to avoid conflicts in bounty submissions file paths
WORKDIR /root

ADD . /yummy-harmony

RUN yum update -y && yum install -y git rpmdevtools ; cd /root && git clone https://github.com/ranmses/gc-b71 ; 