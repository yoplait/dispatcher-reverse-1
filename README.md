# dispatcher-reverse-1

dispatcher-reverse-1
===================================

Tutorial
---------


[Docker compose : AEM Dispatcher reverse proxy with multiple containers](https://www.linkedin.com/in/perezpardojc/) 

docker stop $(docker ps -a -q)


cd site1
docker-compose build
docker-compose pull
docker-compose up -d --no-build
docker-compose up -d

cd ../site2
docker-compose build
docker-compose pull
docker-compose up -d --no-build
docker-compose up -d

cd ../reverse-proxy/
docker-compose build
docker-compose pull
docker-compose up -d --no-build
docker-compose up -d