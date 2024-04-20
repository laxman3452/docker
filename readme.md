**1) Problem Statement**

**2) Installation of the docker CLI.**

docker run -it ubuntu

**3) Understanding images and containers in docker.**

docker container ls
docker container ls -a
docker exec -it pedantic_mendal bash

**4) Running ubunti image in container.**

**5) Multiple containers**

**6) Port Mapping**

docker run -it -p 8025:8025 ubuntu

**7) Environment variables**
docker run -it -p 8080:8080 -e key=value -e key=value ubuntu

**8) Dockerization of  node js application**
a) Dockerfile
b) Caching Layers
c) Publishing to Hub

**9) Docker Compose**
a) Services
b) Port Mapping
c) Env Variables


**10) Docker Networking**
a)Bridge -- need port mapping
b)Host   -- doesn't need port mapping

docker network inspect bridge
run containers to see which container using bridge networking

docker network ls

docker run -it --network=host busybox
to make busybox run in host network i.e no need to do port mapping explicitly.

**11) Volume Mounting --not destroy internal files even if container is destroyed.**

**12) Efficient Caching in layers. to optimize dockerfile instructuctions like which cmnd to run first.**


**13) Docker Multi-stage build**
 typescript build

 docker run -it --name my_container busybox




 node_modules
 .dockerignore
 docker-compose.yml
 Dockerfile
 main.js
 package-lock.json
 package.json


 Dockerfile

 RUN apt-get install -y curl
 RUN (install node url)
RUN apt-get upgrade-y
RUN apt-get install -y node js

WORKDIR /app

COPT package-lock.json package-lock.json
COPY package.json package.json

RUN npm install 

COPY main.js main.js

ENTRYPOINT ["node","main.js"]

