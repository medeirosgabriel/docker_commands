# **Docker Commands - Study**

# **Containers**

- ## sudo docker container run -p 8080:80 nginx -> Executa container na porta 8080

- ## sudo docker container  run -d -p 8080:80 <IMAGE> -> Executar container em segundo plano (nao perde o terminal)

- ## sudo docker container ls -> Containers executando

- ## sudo docker container ls -a -> Todos os containers

- ## sudo docker container stop <CONTAINER_ID> -> Para o container

- ## sudo docker container rm -f $(sudo docker container ls -a -q) -> Remove todos os containers que não estão executando

- ## sudo docker container  run -d -P <IMAGE> -> Executar container em segundo plano na porta (nao perde o terminal) em uma porta aleatória

- ## sudo docker container run -d -p 80:80 --name <CONTAINER_NAME> <HOST>

- ## sudo docker container logs <CONTAINER_NAME> -> Olha o último log

- ## sudo docker container logs -f <CONTAINER_NAME> -> Acompanha os logs no terminal

- ## sudo docker container top <CONTAINER_NAME> -> Processos que um container está executando

- ## sudo docker container stats -> Status dos recursos de um container

- ## sudo docker container stats <CONTAINER_NAME>

- ## sudo docker container inspect <CONTAINER_NAME> -> Informações a respeito do container

- ## sudo docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' <CONTAINER_ID> -> Endereço IP

# **Redes**

- ## **Tipos de Redes:** 
    - ## **Rede Bridge:** 
        - ## Rede padrão entre containers 
        - ## Comunicação interna entre containers. 
        - ## Uma para cada aplicação. 
        - ## Exemplo: Front e Back

    - ## **Rede Host:** Essa rede tem como objetivo entregar para o container todas as interfaces existentes no docker host

    - ## **Rede None:** Não possui acesso externo e nem de outros containers

- ## sudo docker network ls -> Lista as redes criadas

- ## sudo docker container run --name <CONTAINER_NAME> -d --network <NETWORK_NAME> <IMAGE>

- ## sudo docker network inspect <NETWORK_NAME> -> Informações da rede

- ## sudo docker container exec -it <CONTAINER_NAME> sh -> Executa o terminal do container

- ## sudo docker network create <NETWORK_NAME> -> Cria uma rede

- ## sudo docker network create <NETWORK_NAME> --subnet 192.168.134.0/24 --gateway 192.168.134.1 -> Cria uma rede com subnet e gateway

- ## sudo docker network rm <NETWORK_NAME> -> Remove uma rede

- ## sudo docker network prune -> Remove as redes que não estão sendo utilizadas
