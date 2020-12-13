# Docker

## Portainer

```
docker volume create portainer_data

docker run -d -p 8000:8000 -p 9000:9000 --name=portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce

```

## MySQL

```
docker volume create --name mysql_data

docker run --name=mysql -p 3306:3306 -e MYSQL_ROOT_HOST=% -e MYSQL_ALLOW_EMPTY_PASSWORD=true -v mysql_data:/var/lib/mysql -d mysql/mysql-server

docker exec -it mysql mysql

ALTER USER 'root' IDENTIFIED WITH mysql_native_password BY '';
```

## Kafka & Zookeeper

- Build Image from Dockerfile [https://github.com/pornpol/docker-kafka-zookeeper]

## Redis

```
docker volume create --name redis_data
docker run -d -v redis_data:/data --name redis -p 6379:6379 redis
```
