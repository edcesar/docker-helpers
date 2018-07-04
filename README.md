Para ou remove todos os containers:
docker stop $(docker ps -a -q)
docker rm $(docker ps -a -q)
