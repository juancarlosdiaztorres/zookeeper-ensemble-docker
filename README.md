# Zookeeper-ensemble using Docker-compose
Docker based Zookeeper managed by Docker-compose. Zookeeper version: 3.14.

## Steps to reproduce the environment
1. docker-compose up -d --build
2. Check containers with docker ps -a
3. See container /tmp/myid file using docker exec -it {container-id} /bin/bash
4. Check networks and zServers IP addresses using docker network inspect {network-id} [sudo docker network inspect zookeeper-ensemble-docker_default]

At this point, Zookeeper is alive with a 3-quorum ensemble using 3 Docker containers using the IP addresses shown in docker-compose.
Furthermore, there are another 3 bank-containers running the App.

Since it's using "link", reaching a container from another one can be done by simply using the name. For example: ping bank2

## Assigned IPs:
- zoo1: 10.0.0.2
- zoo2: 10.0.0.3
- zoo3: 10.0.0.4
- bank1: 10.0.0.5
- bank2: 10.0.0.6
- bank3: 10.0.0.7

Now it is possible to access to its API. Just download Zookeeper (v.3.4.14 has been used here) and run bin/zkCli.sh
