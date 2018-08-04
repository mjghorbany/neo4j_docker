# About

Neo4j is a popular graph database.

# Setup

* Follow Docker setup directions explained in Elasticsearch repo ([here](https://github.com/accenture-ops-ai/elasticsearch-docker))
* Install and run neo4j:
``` shell
sudo docker run -d \
    --name neo4j_docker \
    --publish=7474:7474 \
    --publish=7687:7687 \
    --publish=7473:7473 \
    --publish=1337:1337 \
    --volume=$HOME/neo4j/data:/data \
    --volume=$HOME/neo4j/logs:/logs \
    --volume=$HOME/neo4j/import:/var/lib/neo4j/import \
    --volume=$HOME/neo4j/conf/:/conf/ \
    --restart=always \
    neo4j:3.3
```
* Temporarily open port 7474 and 7687
* Click the play button in upper right corner, sign in with default `neo4j:neo4j`. Then choose new pw `accenture-ops`.
* No Go to <http://localhost:7474> and clock the gear icon in lower left side. 
  - Select the box "Do not use Bolt". (For version 3.1)
  - Make sure to open port 7687 which is the port for Bolt. (For version 3.3, "Do not use Bolt" can not be selected.)
* Now close port 7474 and 7687 if you no longer connect to the neo4j server via web interface.


# Useful Docker commands

* List Docker containers
  - `sudo docker ps`
* Stop Docker container
  - `sudo docker stop <CONTAINERID>`
* Start Docker container
  - `sudo docker start <CONTAINERID>`
* Stop and Remove all Docker containers
  - `sudo docker stop $(sudo docker ps -a -q)`
  - `sudo docker rm $(sudo docker ps -a -q)`
  - !danger `sudo docker rmi --force $(sudo docker images -a -q)`

# Use

* Python API: https://neo4j.com/developer/python/
  - `pip install neo4j-driver`
* docs: http://neo4j.com/docs/developer-manual/current/drivers/	


# Resources

* https://neo4j.com/developer/docker/
* https://store.docker.com/images/neo4j?tab=description
