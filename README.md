## Redis Docker image with spiped encryption

 docker build -t redis:0.1 .

 docker run -d -e REDIS_PASSWORD="abcd@123456789" -p 6387:6377 --name redis redis:0.1 

 docker ps -a | grep redis

Check

 redis-cli -h 0.0.0.0 -p 6387 

 0.0.0.0:6387> auth abcd@123456789
 OK

 docker run -d -e REDIS_PASSWORD="abcd@123456789" -v /redis/data:/data -p 6387:6377  --name redis redis:0.2
