This repo will be used to build the image necessary for the producer and consumer of the sc4-pilot.

ENV variables will have to be specified to the containers.

Producer:
FLINK_APPLICATION_MAIN_CLASS: "eu.bde.pilot.sc4.fcd.FlinkFcdProducer"
FLINK_APPLICATION_ARGS: "--path hdfs://namenode:8020/user/hue/taxi_sample_100k.txt --topic taxi"

Consumer:
FLINK_APPLICATION_MAIN_CLASS: "eu.bde.pilot.sc4.fcd.FlinkFcdConsumer"
FLINK_APPLICATION_ARGS: "--topic taxi --window 2 --sink hdfs://namenode:8020/user/hue/taxi_aggregates.txt --elasticsearch_endpoint elasticsearch --elasticsearch_port 9300"
