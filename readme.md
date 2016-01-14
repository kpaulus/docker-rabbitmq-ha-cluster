This folder structure contains the Dockerfiles for building RabbitMQ cluster with HAproxy running - the number of nodes are completely customizable using https://docs.docker.com/compose/[docker-compose] docker-compose.yml file.


Structure:
==========
There are 3 folders.

1. base - this is the base Dockerfile which builds on a CentOS image and installs the RabbitMQ binaries on the image
2. server - This builds on the base image and has the startup script for bring up a RabbitMQ server
3. cluster - This contains a https://docs.docker.com/compose/[docker-compose] definition file(docker-compose.yml) for brining up the rabbitmq cluster. Use `docker-compose up -d` to bring up the cluster.
4 haproxy - this is the base Dockerfile which using the haproxy image and configures it using haproxy.cfg


Running the Cluster:
===============================
Once the images are built, boot up the cluster using the docker-compose.yml configuration provided in cluster folder:    

[source]
----
docker-compose up
----

By default haproxy and rabbitmq 3 nodes as a cluster are started up this way

RabbitMq Managment - http://localhost:8080
haproxy stats - http://localhost:1936
mqtt - localhost:1936
amqp - localhost:5672

if needed, additional nodes can be added to cluster/docker-compose.yml

    
