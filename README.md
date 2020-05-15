
# Docker version 19.03.5, build 633a0ea
docker --version

# docker-compose version 1.25.4, build 8d51620a
docker-compose --version

# ejecutar los contenedores, se usa --compatibility por usar la key deploy en docker-compose.yml
docker-compose --compatibility up -d cassandra-service  
docker-compose --compatibility up -d rabbitmq-service  
docker-compose --compatibility up -d zipkin-service  

# entrar al contener con bash o sh por servicio
docker-compose --compatibility exec cassandra-service sh  
docker-compose --compatibility exec rabbitmq-service sh  
docker-compose --compatibility exec zipkin-service bash  

# logs de los servicios
docker-compose --compatibility logs -f cassandra-service  
docker-compose --compatibility logs -f rabbitmq-service  
docker-compose --compatibility logs -f zipkin-service  
docker-compose --compatibility logs -f --tail 100  
docker-compose --compatibility logs -f --tail 10  cassandra-service  
