# Solo los que estan iniciados
docker ps
# Para ver todos los contenedores
docker ps -a
# Ver las imagenes
docker images
# Eliminar todos los contenedores que no estan en uso
docker container prune
# Eliminar imagen sin nombre 
docker image prune
# Eliminar una imagen
docker rmi <Nombre:Tag || Id de la imagen>
# Eliminar contenedores que no estan en uso
docker rm <Nombre:Tag || Id del contenedor>
# Pausar un contenedor
docker stop <Nombre:Tag || Id del contenedor>
# Iniciar un contenedor
docker start <Nombre:Tag || Id del contenedor>
# Acceder al contenedor
docker exec -it <id del contenedor || nombre:tag> sh
# Ver logs
docker container logs <nombre || Id del contenedor>

Pasos para levantar un contenedor

1 - Crear la imagen

docker build -t <Nombre que tendra la imagen> .

2 - Correr el contenedor 

docker run --name <Nombre que tendra el contenedor> -p "Puerto Externo:PuertoInterno" -e "ASPNETCORE_ENVIRONMENT=Production" -d <Nombre de la imagen>

3 - Para bases de datos se deben de agregar las siguientes lineas

-e "ACCEPT_EULA" -e "SA_PASSWORD=<CLAVE>" 

Para conectarse a una base de datos dentro de docker se usa el puerto 14333

# Levantar compose
docker compose up -d
# Levantar compose sin reiniciar contenedores
docker compose up -d --no-deps
