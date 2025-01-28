# RENIE

Acá vamos a Documentar la BBDD RENIE

## Servidor
Se usará un servidor Local hasta poder configurarlo nuevamente en un servidor publico

Host: 10.97.247.69

Base: mapa

## Carpeta scripts

Contiene los scripts de consulta y actualización de la base

## Wiki

Contiene ola documentación de la base.

## Conectar usuario a servidor local
Pasos para configurar el acceso remoto a PostgreSQL

#### 1. Editar el archivo postgresql.conf:
Ubicación típica en Windows: C:\Program Files\PostgreSQL\{versión}\data\postgresql.conf
Buscá la línea que dice:
#listen_addresses = 'localhost'
Cambiala por:
listen_addresses = '*'

#### 2. Configurar el archivo pg_hba.conf:
Ubicación típica: misma carpeta que postgresql.conf.
Agregá una línea al final 
host    all    all    (ip del que se va a conectar)/24    md5

#### 3. Reiniciar el servicio de PostgreSQL:
Servicios > Postgres > reiniciar

#### 4. Configurar el firewall de tu PC:
Abrir el Panel de Control
Ir a Sistema y seguridad
Seleccionar Firewall de Windows
Hacer clic en Configuración avanzada
Seleccionar Reglas de entrada
Hacer clic en Nueva regla
Elegir Puerto como el tipo de regla
Seleccionar TCP como el protocolo
Ingresar 5432 como el número de puerto
Hacer clic en Siguiente
Seleccionar Permitir la conexión
Configurar los perfiles según sea necesario
Ingresar un nombre y una descripción para la regla
Hacer clic en Finalizar

#### 5. Crear usuario en PG:
Click derecho sobre el nombre de tu servidor
Crear Rol de login
En General: nombre de usuario
En Definición: password de usuario
En Privilegios: asignar

#### 6. Seteo del usuario:
IP de la  del servidor local
usuario
passwpord
5432
