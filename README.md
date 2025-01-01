# Docker Registry

Then, create a subdirectory called data, where your registry will store its images:
````
mkdir data
````

we need to install passwd:
````
sudo apt-get update
sudo apt-get install apache2-utils
mkdir auth
cd auth
````

set user:
````
htpasswd -Bc registry.password username
````

To add more users, re-run the previous command without -c, which creates a new file:
````
htpasswd -B registry.password username
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

reference:

https://www.digitalocean.com/community/tutorials/how-to-set-up-a-private-docker-registry-on-ubuntu-20-04