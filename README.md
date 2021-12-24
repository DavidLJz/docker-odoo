# Instrucciones para instalar
## 1. Instalar docker y docker-compose. 

```
https://www.docker.com/get-started
```

## 2. Al terminar, ejecutar el seguimiento comando
```
docker-compose run web bash
```

## 3. Se ejecuta el terminal de odoo. Introducir el siguiente comando
```
odoo --init base --database odoo --stop-after-init --db_host=database --db_user odoo --db_password strongpass
```

Salir usando CTRL + D

## 4. Desde consola de comando o con Docker hacer el build de la imagen
Esperar a que se termine de ejecutar el build

```
docker-compose up -d
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
