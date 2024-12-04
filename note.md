## 测试环境启动命令变更

`docker network create looklook_net`

`docker-compose -f docker-compose-env.yml start`
`docker-compose -f docker-compose.yml start`

`docker-compose  -f docker-compose-env.yml stop`
`docker-compose  -f docker-compose.yml stop`


./kafka-topics.sh --create --bootstrap-server kafka:9092 --replication-factor 1 --partitions 1 --topic looklook-log
./kafka-topics.sh --create --bootstrap-server kafka:9092 --replication-factor 1 --partitions 1 --topic payment-update-paystatus-topic



yugu@yugudeMacBook-Pro go-zero-looklook % docker exec -it kafka /bin/sh
/ $ cd /opt/kafka/bin/
/opt/kafka/bin $ ./kafka-topics.sh --create --zookeeper zookeeper:2181 --replication-factor 1 -partitions 1 --topic looklook-log
zookeeper is not a recognized option
joptsimple.UnrecognizedOptionException: zookeeper is not a recognized option
at joptsimple.OptionException.unrecognizedOption(OptionException.java:108)
at joptsimple.OptionParser.handleLongOptionToken(OptionParser.java:510)
at joptsimple.OptionParserState$2.handleArgument(OptionParserState.java:56)
at joptsimple.OptionParser.parse(OptionParser.java:396)
at org.apache.kafka.tools.TopicCommand$TopicCommandOptions.<init>(TopicCommand.java:830)
at org.apache.kafka.tools.TopicCommand.execute(TopicCommand.java:100)
at org.apache.kafka.tools.TopicCommand.mainNoExit(TopicCommand.java:90)
at org.apache.kafka.tools.TopicCommand.main(TopicCommand.java:85)

/opt/kafka/bin $ ./kafka-topics.sh --create --bootstrap-server kafka:9092 --replication-factor 1 --partitions 1 --topic looklook-log
Error while executing topic command : Topic 'looklook-log' already exists.
[2024-12-04 06:23:49,820] ERROR org.apache.kafka.common.errors.TopicExistsException: Topic 'looklook-log' already exists.
(org.apache.kafka.tools.TopicCommand)
/opt/kafka/bin $ ./kafka-topics.sh --create --bootstrap-server kafka:9092 --replication-factor 1 --partitions 1 --topic payment-update-paystatus-topic
Created topic payment-update-paystatus-topic.
