# Local Kafka docker container setup
This repo contains a simple docker compose setup to quickly setup a local kafka broker.
Simply run the following step and you should be good to go.
```
git clone https://github.com/oemergenc/dc-kafka.git
cd dc-kafka
docker-compose up
```
## Test with kafka-cli
Make sure you have kafka-cli installed. After starting the docker-compose setup, simply run the following cmd
to list all available topics. By default only the topic `testopic` is created.
```
kafka-topics --zookeeper 127.0.0.1:2181 --list
testtopic
```
