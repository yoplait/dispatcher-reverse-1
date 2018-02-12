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

cd ../site2
docker-compose build
docker-compose pull
docker-compose up -d --no-build

cd ..

cd ../reverse-proxy/

docker build -t perezpardojc/dispatcher .

docker-compose build
docker-compose pull
docker-compose up -d --no-build
docker-compose up -d


dispatcherreverse1_proxy
docker run -it -p 80:80 --entrypoint=/bin/bash dispatcherreverse1_proxy -i

/usr/sbin/httpd
netstat -plnt
service httpd status
service httpd restart

/etc/httpd
/var/www/html

vi /etc/httpd/conf/httpd.conf
vi /etc/httpd/conf/dispatcher.any

tail -f /var/log/httpd/access_log
tail -f /var/log/httpd/error_log
tail -f /var/log/httpd/dispatcher.log


curl 172.17.0.2
curl 172.17.0.3
curl 172.17.0.4

curl 172.20.0.2
ping 172.20.0.2