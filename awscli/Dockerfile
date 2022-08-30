FROM ubuntu:latest

MAINTAINER Juha Leivo

RUN apt-get update && apt-get install debconf-doc -y
RUN DEBIAN_FRONTEND=noninteractive apt-get install awscli curl vim -y
RUN curl "https://s3.amazonaws.com/session-manager-downloads/plugin/latest/ubuntu_64bit/session-manager-plugin.deb" -o "session-manager-plugin.deb"
RUN dpkg -i session-manager-plugin.deb
RUN rm session-manager-plugin.deb

