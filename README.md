# Instrucciones para instalar
## 1. Instalar docker y docker-compose. 

```
https://www.docker.com/get-started

```

## 2. Desde la consola de comando hacer el build de la imagen
```
docker-compose up -d
```

## 3. Al terminar, ejecutar el siguiente comando
```
docker exec -ti odoo-web bash
```

## 4. Se ejecuta el terminal de odoo. Introducir el siguiente comando
```
odoo --init base --database dbname --stop-after-init --db_host=db --db_user dbuser --db_password dbpass
```
Los parametros de este comando corresponden a los parametros de conexión en .env y docker-compose.yaml

Salir usando CTRL + D

## 6. Reiniciar los contenedores
Hay que reiniciar los contenedores para ver los cambios, user el siguiente comando
```
docker-compose stop && docker-compose up -d
```

## 5. Se ejecuta el servidor de docker
Acceder a la siguiente URL: http://localhost:8069

Introducir las siguientes credenciales:
USER: admin
PASS: admin

## Parametros en archivo .env
El archivo .env debe estar en el directorio donde se encuentra este archivo
- COMPOSE_PROJECT_NAME: Es el nombre del contenedor y la imagen
- ODOO_VERSION: Versión de Odoo
- ODOO_PORT: Puerto que ocupará Odoo
- POSTGRES_USER: Nombre de usuario para acceder a database (dbuser)
- POSTGRES_PASSWORD: Contraseña para database (dbpass)
- POSTGRES_DB: Nombre de la base de datos (dbname)
- POSTGRES_VERSION: Versión de Postgres


## Inyectar SQL durante instalación de imagen
Cualquier archivo SQL que se encuentre en el siguiente directorio se ejecutara dentro la base de datos durante el build de la imagen. 
```
./postgresql/dumps
```
Es posible que se sobreescriba por la instalación de Odoo.

## Configurar Odoo
Editar odoo.conf en el siguiente directorio
```
./odoo/config/odoo.conf
```
