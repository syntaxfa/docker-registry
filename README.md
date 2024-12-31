# Docker Registry

First we need to install passwd:
````
sudo apt-get update
sudo apt-get install apache2-utils
mkdir -p ./auth ./data
````

set user:
````
htpasswd -c ./auth/htpasswd username
````

if you want to create a new user:
````
htpasswd ./auth/htpasswd username
````

Running:
````
docker-compose up -d
````

test:
````
docker login localhost:5000

docker tag felan-chiz localhost:5000/felan-chiz

docker push localhost:5000/felan-chiz

docker pull localhost:5000/felan-chiz
````
