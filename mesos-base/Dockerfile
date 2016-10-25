FROM ubuntu:16.04
RUN echo 'Asia/Shanghai' > /etc/timezone && rm /etc/localtime && dpkg-reconfigure -f noninteractive tzdata

# Install dependancies
RUN apt-key adv --keyserver keyserver.ubuntu.com --recv E56151BF
RUN apt-get -y update 
RUN apt-get -y install curl python-setuptools python-pip python-dev python-protobuf lsb-release

RUN DISTRO=$(lsb_release -is | tr '[:upper:]' '[:lower:]');CODENAME=$(lsb_release -cs);echo "deb http://repos.mesosphere.com/${DISTRO} ${CODENAME} main" | tee /etc/apt/sources.list.d/mesosphere.list

#RUN sed -i 's/archive.ubuntu.com/cn.archive.ubuntu.com/g' /etc/apt/sources.list
