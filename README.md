# Zookeeper-ensemble using Docker-compose
Docker based Zookeeper managed by Docker-compose. Zookeeper version: 3.14.

How to deploy:
1. docker-compose up -d --build
2. Check containers with docker ps -a
3. See container /tmp/myid file using docker exec -it {container-id} /bin/bash
4. Check networks and zServers IP addresses using docker network inspect {network-id} [sudo docker network inspect zookeeper-ensemble-docker_default]

At this point, Zookeeper is alive with a 3-quorum ensemble using 3 Docker containers using the following IP addresses:	172.18.0.2, 172.18.0.3 and 172.18.0.4.

5. After that, it is time to configure ENV-VARs following CNVR Zookeeper Lab (page 4):
	- Decompress file "tar xvfz zookeeper.tar.gz"
	- Classpath config: "export CLASSPATH=$CLASSPATH:/home/jc/Desktop/cnvr/zoo/zookeeper-ensemble-docker/zookeeper-3.4.14/zookeeper-3.4.14.jar" and "export CLASSPATH=$CLASSPATH:/home/jc/Desktop/cnvr/zoo/zookeeper-ensemble-docker/zookeeper-3.4.14/lib/*".
	- "export PATH=$PATH:/home/jc/Desktop/cnvr/zoo/zookeeper-ensemble-docker/zookeeper-3.4.14/bin"

After that, Zk ensemble is mounted and accesible using zkCli.sh.

6. Modify /etc/hosts and add the following statement to create a DNS for Zknodes:

	
Zookeeper nodes
172.18.0.2      zoo1
172.18.0.3      zoo2
172.18.0.4      zoo3

7. Create a client using "zkCli.sh -server zoo1:2181"




