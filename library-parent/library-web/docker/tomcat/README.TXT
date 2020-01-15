# Construire l'image
docker build -t library-tomcat:8.5.47 .

#Demarrer un conteneur docker 
docker run -d --rm -p 8080:8080 --name  tomcat-server1  library-tomcat:8.5.47

#Arreter le conteneur 
docker stop tomcat-server1


# le lien entre mysql et tomcat avec l'option --link
docker run -d --rm -p 8080:8080 --name  tomcat-server1 --link mysql-server:mysql  library-tomcat:8.5.47