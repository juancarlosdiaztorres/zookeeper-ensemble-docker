# Zookeeper-ensemble using Docker-compose
Docker based Zookeeper managed by Docker-compose. Zookeeper version: 3.14.

How to deploy:
1. docker-compose up -d --build
2. Check containers with docker ps -a
3. See container /tmp/myid file using docker exec -it {container-id} /bin/bash
4. Check networks and zServers IP addresses using docker network inspect {network-id}


