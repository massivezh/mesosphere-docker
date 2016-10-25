#FROM vtajzich/mesosphere-docker-mesos-base	
FROM mesos-base

# Installing zookeeper.  Seems to be a dependancy to mesos
# Not going to start it on runtime though
RUN apt-get -y update 
RUN apt-get -y install zookeeperd wget apt-transport-https
RUN echo 1 | dd of=/var/lib/zookeeper/myid

# Install mesos.
RUN apt-get -y install mesos
RUN mkdir -p /etc/mesos-master
RUN echo in_memory | dd of=/etc/mesos-master/registry

RUN curl -sSL https://get.docker.com/ | sh

# Not exposing port b/c you have to run the master in bridge net mode
#EXPOSE 5050

ENTRYPOINT ["mesos-master"]
