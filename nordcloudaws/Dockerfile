FROM ubuntu:latest

LABEL org.opencontainers.image.authors="Juha Leivo"

RUN apt-get update && apt-get install debconf-doc -y
RUN DEBIAN_FRONTEND=noninteractive apt-get install curl vim unzip wget -y
RUN apt-get -q -y clean
RUN rm -rf /var/cache/apt/archives/* /var/lib/apt/lists/*
RUN curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "/tmp/awscliv2.zip"
RUN (cd /tmp; unzip awscliv2.zip)
RUN (cd /tmp; ./aws/install)
RUN rm -rf /tmp/aws*
RUN (CURRENT_VERSION=$(curl -Ls https://api.github.com/repos/Versent/saml2aws/releases/latest | grep 'tag_name' | cut -d'v' -f2 | cut -d'"' -f1); wget -c https://github.com/Versent/saml2aws/releases/download/v${CURRENT_VERSION}/saml2aws_${CURRENT_VERSION}_linux_amd64.tar.gz -O /tmp/saml2aws_linux_amd64.tar.gz)
RUN tar -xzf /tmp/saml2aws_linux_amd64.tar.gz -C /usr/local/bin
RUN chmod a+x /usr/local/bin/saml2aws
ENTRYPOINT [ "/usr/local/bin/saml2aws" ]