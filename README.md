# CICD_DOCKER_COMPOSE



Ex: Docker-compose file for setting up CI-CD Environment.
jenkins container is linked with two tomcat containers 


# vim docker-compose.yml

---
version: '3'
services:
 devserver:
  image: jenkins
  ports:
   - 7070:8080

 qaserver:
  image: tomee
  ports:
   - 8899:8080
  links:
   - devserver:jenkins


 prodserver:
  image: tomee
  ports:
   - 9090:8080
  links:
   - devserver:jenkins
...


:wq

# docker rm -f $(docker ps -aq)
# docker-compose up -d

# docker container ls

To check
public_ip:7070  ( To check jenkins )
public_ip:8899 ( Tomcat  qa server )
public_ip:9090 ( Tomcat  prod server )

+++++++++++++++++++++



