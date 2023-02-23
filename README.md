# kafka docker


## Docker-compose
- This from [official document](https://developer.confluent.io/quickstart/kafka-docker/)
- Start kafka broker:
```commandline
docker-compose up -d
```

- Create topic:
```commandline
docker exec broker \
kafka-topics --bootstrap-server broker:9092 \
             --create \
             --topic quickstart
```

- Write message to the topic:
```commandline
docker exec --interactive --tty broker \
kafka-console-producer --bootstrap-server broker:9092 \
                       --topic quickstart
```

- Insert following message and press: `Ctrl + D` when you finished:

```commandline
this is my first kafka message
hello world!
this is my third kafka message. Im on a roll D
```

- Read message from the topic:

```commandline
docker exec --interactive --tty broker \
kafka-console-consumer --bootstrap-server broker:9092 \
                       --topic quickstart \
                       --from-beginning
```

- Write some more messages:

```commandline
docker exec --interactive --tty broker \
kafka-console-producer --bootstrap-server broker:9092 \
                       --topic quickstart
```

- Stop the kafka broker:

```commandline
docker-compose down
```

## kafka python client
- From this official [getting started](https://developer.confluent.io/get-started/python/)
