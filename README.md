### Parar ou remover todos os containers:
- docker stop $(docker ps -a -q)  
- docker rm $(docker ps -a -q)  
  
### Cria um container, nginx, expondo a porta 80, com um volume sincronizado ao host, de nome nginx
- docker run -d -p 80:80 -v /home/www:/usr/share/nginx/html --name nginx nginx  
  
### Entra no container de nome nginx
- docker exec -it nginx bash  

### Instala Mysql, seta senha de root, cria base de dados e atribui tag 5.7
- docker run --name dbserver -e MYSQL_ROOT_PASSWORD=root -e MYSQL_DATABASE=wordpress -d mysql:5.7  

### Instala wordpress e linka com container do mysql, expondo a porta 80
- docker run --name wordpress --link dbserver:mysql -d -p 80:80 wordpress

