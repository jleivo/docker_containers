FROM ubuntu:latest

MAINTAINER Juha Leivo

RUN apt-get update && apt-get install debconf-doc -y
RUN DEBIAN_FRONTEND=noninteractive apt-get install curl vim unzip git -y
RUN curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "/tmp/awscliv2.zip"
RUN (cd /tmp; unzip awscliv2.zip)
RUN (cd /tmp; ./aws/install)
RUN rm -rf /tmp/aws*
RUN curl "https://s3.amazonaws.com/session-manager-downloads/plugin/latest/ubuntu_64bit/session-manager-plugin.deb" -o "session-manager-plugin.deb"
RUN dpkg -i session-manager-plugin.deb
RUN rm session-manager-plugin.deb
