# start the server 
docker-compose up

# connect to kafka 
docker-compose exec kafka /bin/bash

# add topic
kafka-topics.sh --create --zookeeper zookeeper:2181 --replication-factor 1 --partitions 1 --topic my-topic


# add event 
kafka-console-producer.sh --broker-list localhost:9092 --topic my-topic

then send messages

# consume event
kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic my-topic --from-beginning

and consume messages

