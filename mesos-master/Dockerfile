FROM sumanganta/mesosphere-docker-base-image

# Installing zookeeper.  Seems to be a dependancy to mesos
# Not going to start it on runtime though
RUN sudo apt-get -y install zookeeperd
RUN echo 1 | sudo dd of=/var/lib/zookeeper/myid

# Install mesos.
RUN sudo apt-get -y install mesos
RUN sudo mkdir -p /etc/mesos-master
RUN echo in_memory | sudo dd of=/etc/mesos-master/registry

# Not exposing port b/c you have to run the master in bridge net mode
#EXPOSE 5050

#install docker
RUN curl -sSL https://get.docker.com/ | sh

ENTRYPOINT ["mesos-master"]
