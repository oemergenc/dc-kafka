# Local Kafka docker container setup
This repo contains a simple docker compose setup to quickly setup a local kafka broker.
Simply run the following step and you should be good to go.
```
git clone https://github.com/oemergenc/dc-kafka.git
cd dc-kafka
docker-compose up
```
## Kafka UI
The setup contains a web ui, which allows to quickly inspect topics of the broker
Simply open the following url from your host machine and you should be able to acces the ui
```
http://127.0.0.1:8000
```

## Test with kafkacat container
After starting the docker setup you can run the following command to check if the kafka 
broker is reachable from your host machine
```
docker run --tty \
           --network dc-kafka_default \
           confluentinc/cp-kafkacat \
           kafkacat -b kafka:9093 \
                    -L
```
## Test with native kafka-cli
Make sure you have kafka-cli installed. After starting the docker-compose setup, simply run the following cmd
to list all available topics. By default only the topic `testopic` is created.
```
kafka-topics --zookeeper 127.0.0.1:2181 --list
testtopic
```
