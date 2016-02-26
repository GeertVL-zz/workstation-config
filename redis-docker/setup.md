# configure Vagrantfile 
See the enclosed one as an example.

# docker setup
## Redis server
sudo docker run --name ewmsredis -d -i -p 6379:6379 -t ewms/redis

## Redis client
sudo docker run --rm -it --link ewmsredis:redis redis /bin/bash
data> redis-cli -h redis -p 6379

## RabbitMQ
sudo docker run -d --hostname my-rabbit --name some-rabbit -p 8080:15672 rabbitmq:3-management
