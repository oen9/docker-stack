# docker-stack
Ready to use docker config

## mongodb
### start
`docker-compose up -d mongo-express`
### on localhost
`mongodb://root:secret@localhost:27017/admin`
### inside docker
`mongodb://root:secret@mongo:27017/admin`
### mongo express
`http://localhost:8081/`

## kafka
### start
`docker-compose up -d --scale kafka=3 zookeeper kafka`
### into the docker
`docker-compose run kafka bash`\
`./opt/kafka/bin/kafka-console-consumer.sh --bootstrap-server kafka:9092 --topic test`\
`./opt/kafka/bin/kafka-console-producer.sh --bootstrap-server kafka:9092 --topic test`

## postgres
### start
`docker-compose up -d postgres`
### into the docker
`docker-compose run postgres bash`\
`psql -h postgres -d mydbname -U root`

## pgadmin
### start with postgres
Before first start:\
`mkdir -p cache/pgadmin`\
`chown -R 5050:5050 cache/pgadmin`\
Other starts:\
`docker-compose up -d pgadmin`
### into the docker
`docker-compose run postgres bash`\
`psql -h postgres -d mydbname -U root`
