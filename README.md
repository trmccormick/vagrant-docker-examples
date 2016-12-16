# vagrant-docker-examples
Setup for Vagrant Docker Development Environment

# docker host
before bringing up any of the dockers bring up the docker-host-vm.
If you forget to bring up the host vagrant will try to bring up the host when you vagrant
up but I have noticed that it will fail the host will be running but you will need to
vagrant up again for the docker to start.

# docker virtual network
Setup the docker virtual network so that the containers can connect to mysql
1 - create new network
$ docker network create <network-name>

2 - Connect containers to network
$ docker network connect <network-name> <container-name>

# checking running dockers
vagrant ssh into the docker-host-vm then run docker ps this will list all running dockers.

# running command in dockers
vagrant ssh into the docker-host-vm then run docker exec -t <container-name> <commands>
