In Console 1, enter:

sudo bin/zookeeper-server-srt.sh config/zookeeper.properties

-------------------------------------------
In console 2: enter:

sudo bin/kafka-server-srt.sh config/server.properties

-------------------------------------------
In console 3: enter:

sudo bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic my-topic

-------------------------------------------
After all the above steps, start "KafkaProducerApp".  There will be messages output in Console 3


