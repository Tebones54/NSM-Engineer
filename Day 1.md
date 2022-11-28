## Day 1 Notes
-------------------

**Admin info**
* Laptop login - student:training
* 172.16.40.0/24 - student group
* rocknsm.io - System diagram. Reference this after class is over if you can't remember what feeds into what.


**Fun Facts**

* AF_PACKET has a RAM bottleneck because of the ring buffer.
* Zeek = CPU intensive because of the different logs generated off of the same packet.
* 3 types of traffic - PCAP, alerts, Zeek (human readable metadata)
* google stenography is optimized for write
* Kafka = messaging queue. Should be in all deployments of NSM. Gives a large performance increase over just using logstash. Doesn't do any processing, just queues.
* ELK cannot keep up with the other tools which is why the other stuff exists.
* Logstash does not change the data, only field names. To common schema  (ECS).
* *USE LOGSTASH BECAUSE INGEST NODES COST MONEY*
* Kafka is a disk queue. Which means you don't lose data when it shits the bed.
* Backpressure = notifying the messaging queue to slow down. Logstash recognizes this.
* Partitioning drives for each tool improves performance massively.
* Kafka = topics
* Zookeeper = clustering, used in Kafka.

**Port Numbers (default)**

* Kafka - 9092 (clients. i.e Logstash)
* Stenography - 1234
* Zookeeper - 2181(Kafka),2182,2183(elections)
* Elasticsearch - 9200
* Kibana - 5601
