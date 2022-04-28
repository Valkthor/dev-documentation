# Notes Dockers and Kubernetes

## Definiciones

### Docker-Compose

Es una herramienta para definir y ejecutar aplicaciones Docker multicontenedor que permite simplificar el uso de Docker a partir de archivos YAML.

Se recomienda crear una imagen por cada servicio y luego la orquestacion.

[ Documentacion de DockerFile ]<https://jsitech1.gitbooks.io/meet-docker/content/dockerfiles.html>

## Comandos


docker run -p 80:80 -p 8080:8080 --name billingapp sotobotero/udemy-devops:0.0.1

- para listar imagenes

```powershell
docker image ls
```

- para eliminar una imagen

```powershell
docker image rm 37af101e3eb7
```

- listado de todos los contenedores

    ```powershell
    docker ps -a
    ```

- Listar todas las imagenes

    ```powershell
    docker image ls
    ```

- Eliminar una imagen

    ```powershell
    docker image rm 37af101e3eb7
    ```

- Compilar una imagen
  
```powershell
docker build -t nombreimagen --no-cache --build-arg argumentos
docker build -t billingapp:prod --no-cache --build-arg JAR_FILE=target/*.jar .
```

- Levantar un contenedor a partid de una imagen

    ```powershell
    docker run -p 80:80 -p 8080:8080 --name billingapp billingapp:prod
    ```

- inicializar el contenedor
  
```powershell
docker start <nombre o id>
```

- ver el log de la aplicacion
  
```powershell
dockers logs <nombre o id>
```

- detener el contenedor
  
```powershell
docker stop <nombre o id>
```

## Descargar imagen y montarla

Se puede ir a la pagina <https://hub.docker.com> y luego seleccionar una de las imagenes para descargar. En este ejemplo postgres. Se guarda el archivo YML en alguna carpeta y luego se ejecuta docker-compose.

Para pull e iniciar de inmediato:

```powershell
docker-compose -f stack.yml up
```
Para ejecutar y que no se quede en primer plano:

```powershell
docker-compose -f stack.yml up -d
```


para pull:

```powershell
docker-compose -f stack.yml pull
```

para inciar:

```powershell
docker-compose -f stack.yml pull
```