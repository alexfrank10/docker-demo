cd /path/to/python-docker

pip3 install Flask

pip3 freeze | findstr Flask >> requirements.txt

touch app.py

python -m flask run

touch Dockerfile

docker build --tag docker-python .

docker images

docker tag docker-python:latest docker-python:v1.0.0

docker rmi docker-python:v1.0.0

docker volume create mysql

docker volume create mysql_config

docker network create mysqlnet

Run MySQL in a container and attach to the volumes and network created

```bash
docker run --rm -d -v mysql:/var/lib/mysql \
-v mysql_config:/etc/mysql -p 3366:3306 \
--network mysqlnet \
--name mysqldb \
-e MYSQL_ROOT_PASSWORD=password \
mysql

```

Connect to mysql database inside container
```bash
docker exec -ti mysqldb mysql -u root -p
```