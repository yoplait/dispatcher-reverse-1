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
docker build -t perezpardojc/site1 .
docker build -t perezpardojc/site2 .

docker-compose build
docker-compose pull
docker-compose up -d --no-build
zº

docker exec -it dispatcherreverse1_proxy_1 /bin/bash

dispatcherreverse1_proxy
docker run -it -p 80:80 --entrypoint=/bin/bash dispatcherreverse1_proxy -i

/usr/sbin/httpd
netstat -plnt
service httpd status
service httpd restart
service httpd reload

/etc/httpd
/var/www/html

vi /etc/httpd/conf/httpd.conf
vi /etc/httpd/conf/dispatcher.any

http://site1.example.com/

tail -f /var/log/httpd/access_log
tail -f /var/log/httpd/error_log
tail -f /var/log/httpd/dispatcher.log

curl 172.17.0.2
curl 172.17.0.3
curl 172.17.0.4

curl 172.20.0.2
ping 172.20.0.2


docker run -i --expose=22 b5593e60c33b bash
docker run --name mynginx1 -P -d nginx

docker run --name mynginx1 -v /tmp/perezpardojc/dispatcher-reverse-1/site1:/usr/share/nginx/html:ro -p 81:80 -P -d nginx
docker run --name mynginx2 -v /tmp/perezpardojc/dispatcher-reverse-1/site2:/usr/share/nginx/html:ro -p 82:80 -P -d nginx
docker run -itd --name docker-nginx -p 4503:80 nginx

