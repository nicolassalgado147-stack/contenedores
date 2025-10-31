# Actividad: Contenedores de Bases de Datos con Docker (CMD)

**Alumno:** <Nicolas Salgado>  

## Objetivo
Levantar 3 contenedores (MySQL, MariaDB, PostgreSQL) desde la línea de comandos (CMD), conectarlos con clientes gráficos (DBeaver, HeidiSQL, Beekeeper Studio), crear bases de datos y documentar el proceso con evidencias.

## Comandos Docker usados
Crear contenedor MySQL
docker run -d --name mysql-container -e MYSQL_ROOT_PASSWORD=rootpass -p 3306:3306 mysql:latest

Crear contenedor MariaDB
docker run -d --name mariadb-container -e MARIADB_ROOT_PASSWORD=rootpass -p 3307:3306 mariadb:latest

Crear contenedor PostgreSQL
docker run -d --name postgres-container -e POSTGRES_PASSWORD=rootpass -p 5432:5432 postgres:latest

Ver contenedores activos
docker ps

Acceder al contenedor
docker exec -it nombre_contenedor bash

Detener contenedor
docker stop nombre_contenedor

### Descripcion de cada paso en sql
-d: ejecuta el contenedor en segundo plano.

--name mysql-container: asigna un nombre al contenedor.

-e MYSQL_ROOT_PASSWORD=rootpass: define la contraseña del usuario root.

-p 3306:3306: mapea el puerto 3306 del contenedor al 3306 del host.

mysql:latest: indica que se usará la imagen oficial más reciente de MySQL.

### Descripcion de cada paso en Mariadb
Se usa el puerto 3307 para evitar conflictos con el de MySQL.

Se define la contraseña rootpass para el usuario administrador.

La imagen usada es la oficial mariadb:latest.

### Descripcion de cada paso en postgres
La variable POSTGRES_PASSWORD define la contraseña del usuario postgres.

El puerto 5432 es el predeterminado para PostgreSQL.

Se usa la imagen oficial postgres:latest.

###  Observaciones y conclusiones
Docker permite levantar múltiples servicios de bases de datos de forma simultánea sin conflictos, gracias al uso de puertos diferentes.

Los clientes gráficos DBeaver, HeidiSQL y Beekeeper Studio se conectaron exitosamente a sus respectivos contenedores.

Se validó la creación de bases de datos independientes en cada contenedor.

El uso de variables de entorno simplifica la configuración inicial de contraseñas.

La práctica demuestra la versatilidad de Docker para entornos de desarrollo y pruebas de bases de datos.
