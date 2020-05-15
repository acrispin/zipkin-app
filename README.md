
# Docker version 19.03.5, build 633a0ea
docker --version

# docker-compose version 1.25.4, build 8d51620a
docker-compose --version

# ejecutar los contenedores, se usa --compatibility por usar la key deploy en docker-compose.yml
docker-compose --compatibility up -d cassandra-service  
docker-compose --compatibility up -d rabbitmq-service  
docker-compose --compatibility up -d zipkin-service  

# si exite un cambio en la imagen de un servicio, detener, luego se debe hacer "build" y luego ejecutar el contenedor con "up -d"
docker-compose --compatibility build cassandra-service  
docker-compose --compatibility build rabbitmq-service  
docker-compose --compatibility build zipkin-service  

# logs de los servicios
docker-compose --compatibility logs -f --tail 100 cassandra-service  
docker-compose --compatibility logs -f --tail 100 rabbitmq-service  
docker-compose --compatibility logs -f --tail 100 zipkin-service  

# detener y eliminar contenedores
docker-compose --compatibility rm -fs cassandra-service  
docker-compose --compatibility rm -fs rabbitmq-service  
docker-compose --compatibility rm -fs zipkin-service  

# entrar al contener con bash o sh por servicio
docker-compose --compatibility exec cassandra-service sh  
docker-compose --compatibility exec rabbitmq-service sh  
docker-compose --compatibility exec zipkin-service bash  
