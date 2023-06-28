# kafka-tutorial
Repository for studying kafka

## Kafkaバージョン
3.3

### コンテナ起動
```
docker compose up -d
```

### Kafkaコンテナに入る
```
docker exec -it kafka-tutorial-kafka-1 sh
```

### topic作成コマンド
```
kafka-topics.sh --bootstrap-server=localhost:9092 --create --topic sample-topic --partitions 3 replication-factor 3
```

###topic一覧確認用コマンド
```
kafka-topics.sh --list --bootstrap-server=localhost:9092
```

### メッセージのパブリッシュ
```
kafka-console-producer.sh --bootstrap-server=localhost:9092 --topic sample-topic
```

### メッセージのサブスクライブ
別ターミナルでkafkaに入る
```
docker exec -it kafka-tutorial-kafka-1 sh
```

メッセージのサブスクライブ
```
kafka-console-consumer.sh --bootstrap-server=localhost:9092 --topic sample-topic --from-beginning
```

### topic削除コマンド
```
kafka-topics.sh --bootstrap-server=localhost:9092 --delete --topic sample-topic
```

### コンテナ削除
```
docker-compose down --rmi all --volumes --remove-orphans
```
