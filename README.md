# Laboratorio 02
Hoy utilizaremos docker compose para poder desplegar su trabajo. Servicio web y una
base de datos
## Stack
API
- Minimal API
- Debe retornar un mensaje incluyendo mi nombre
- Docker
- docker run -d --rm -p 3000:3000 nmatsui/hello-world-api. 8c446d43dfc9
focused_wilson
docker run -d --rm -p 3001:3000 nmatsui/hello-world-api sweet_sammet
BD
- PostgreSQL
- $ docker run --name some-postgres -e POSTGRES_PASSWORD=mysecretpassword -d
postgres
# Indicaciones
## Comandos
```bash
docker compose up -d
```
docker compose up --build -d | Contruye la imagen y levanta los servidores.
docker compose ps | Ver los servidores en ejecución.
docker compose exec db pg_isready | Verificar el PostgreSQL.
docker volume ls | Ver los volumenes.
docker compose down | Detener y eliminar los volumenes si estan en uso.

# Comando de las 3 app
curl.exe http://localhost:3000/
curl.exe http://localhost:3001/
curl.exe http://localhost:3002/



## Configuración por entorno
```
MESSAGE=<Gonzales Alex>
```
# Creditos
- Walter Ivan Leturia Rodriguez
# ETC
## Tipos de redes en Docker
bridge: Permite crear contenedores del mismo equipo Docker para que se puedan comunicar entre si por una red virtual.
host: El contenedor usa directamente la red del equipo del anfitrión, por lo q se pierde parte del aislamiento de red.
none: Deja de un lado al contenedor sin conexión de red externa, queda practicamente aislado.
overlay: Permite comunicar contenedores q estan en ejecución en diferentes host de Docker.
macvlan: Permite asignar al contenedor una dirección MAC propia para q en la red pueda parecer un dispositivo fisico independiente.
ipvlan: Permite controlar directamente la asignación de IP de los contenedores y conectarlos a redes externas, con una estructura parecida a la de macvlan pero sin asignar necesariamente una MAC unica a cada contenedor.
## Tipos de volúmenes en Docker
Volumen nombrado: El usuario tiene un nombre definido y docker lo administra. Esto guarda datos de forma persistente aunq el contenedor se elimine
Volumen anónimo: Docker crea aun asi sin q le pongamos nombre especifico. Esto persiste datos más dificles para poder identificarlos y reutilizarlos después.
## Docker
bind mount: Permite conectar una carpeta del equipo con una carpeta del contenedor
tmpfs: Permite guardar información temporalmente en memoria RAM
## Volumen nombrado
postgres_data
Con esto docker termino creando 3lab2_postgres_data