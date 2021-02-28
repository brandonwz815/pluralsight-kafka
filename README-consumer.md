# install kafka_2.13-2.7.0.tgz
# For running KafkaConsumerSubscribeApp and KafkaConsumerAssignApp

cd /usr/local/bin/kafka

sudo bin/kafka-topics.sh \
--zookeeper localhost:2181 \
--alter --topic my-other-topic --partitions 3

sudo bin/kafka-topics.sh \
--zookeeper localhost:2181 \
--alter --topic my-topic --partitions 4

sudo bin/kafka-topics.sh \
--zookeeper localhost:2181 \
--describe


sudo bin/kafka-producer-perf-test.sh \
--topic my-topic \
--num-records 50 \
--record-size 1 \
--throughput 10 \
--producer-props \
bootstrap.servers=localhost:9092 \
key.serializer=org.apache.kafka.common.serialization.StringSerializer \
value.serializer=org.apache.kafka.common.serialization.StringSerializer


sudo bin/kafka-producer-perf-test.sh \
--topic my-other-topic \
--num-records 50 \
--record-size 1 \
--throughput 10 \
--producer-props \
bootstrap.servers=localhost:9092 \
key.serializer=org.apache.kafka.common.serialization.StringSerializer \
value.serializer=org.apache.kafka.common.serialization.StringSerializer
