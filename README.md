### Parar ou remove todos os containers:
- docker stop $(docker ps -a -q)  
- docker rm $(docker ps -a -q)  
  
### Cria um container, nginx, expondo a porta 80, com um volume sincronizado ao host, de nome nginx
- docker run -d -p 80:80 -v /home/www:/usr/share/nginx/html --name nginx nginx  
  
### Entra no container de nome nginx
- docker exec -it nginx bash

