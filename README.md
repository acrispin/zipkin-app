
# Docker version 19.03.5, build 633a0ea
docker --version

# docker-compose version 1.25.4, build 8d51620a
docker-compose --version

# ejecutar los contenedores, se usa --compatibility por usar la key deploy en docker-compose.yml
docker-compose --compatibility up -d cassandra-service  
docker-compose --compatibility up -d rabbitmq-service  
docker-compose --compatibility up -d zipkin-service  

# si exite un cambio en el docker-compose.yml, se debe hacer "build" y luego ejecutar el contenedor con "up -d"
docker-compose --compatibility build cassandra-service  
docker-compose --compatibility build rabbitmq-service  
docker-compose --compatibility build zipkin-service  

# logs de los servicios
docker-compose --compatibility logs -f --tail 100 cassandra-service  
docker-compose --compatibility logs -f --tail 100 rabbitmq-service  
docker-compose --compatibility logs -f --tail 100 zipkin-service  

# entrar al contener con bash o sh por servicio
docker-compose --compatibility exec cassandra-service sh  
docker-compose --compatibility exec rabbitmq-service sh  
docker-compose --compatibility exec zipkin-service bash  
