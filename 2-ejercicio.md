### Crear contenedor de Postgres sin que exponga los puertos. Usar la imagen: postgres:15-alpine3.21
docker run -d --name postgres -e POSTGRES_PASSWORD=snowpoom postgres:15-alpine3.21
### Crear un cliente de postgres. Usar la imagen: dpage/pgadmin4
docker run --name client_pos -e PGADMIN_DEFAULT_EMAIL=jonathan.pagual@hotmail.com -e PGADMIN_DEFAULT_PASSWORD=snowpoom -p 80:80 dpage/pgadmin4

La figura presenta el esquema creado en donde los puertos son:
- a: 80
- b: 80
- c: 5432

![Imagen](esquema-2-ejercicio.PNG)

## Desde el cliente
### Acceder desde el cliente al servidor postgres creado.
<img width="1919" height="870" alt="image" src="https://github.com/user-attachments/assets/4841ad72-57e7-4e90-b6a7-25ac68374c34" />
<img width="896" height="689" alt="image" src="https://github.com/user-attachments/assets/c646eb11-e76e-4a21-8739-5953990d6ee7" />

### Crear la base de datos info, y dentro de esa base la tabla personas, con id (serial) y nombre (varchar), agregar un par de registros en la tabla, obligatorio incluir su nombre.
´´´sql
CREATE DATABASE "info";
--database: info
create table PERSONAS( 
ID SERIAL PRIMARY KEY NOT NULL,
NOMBRE VARCHAR(20) NOT NULL);
´´´
datos:
´´´sql
insert into public.personas(nombre)values('jonathan Pagual'),
('LeoDov#LAN'),
('floor jansen'),
('crispis'),
('kevin wasd'),
('juan chest'),
('snowpoom');
´´´
## Desde el servidor postgresl
### Acceder al servidor
### Conectarse a la base de datos info
# COMPLETAR
### Realizar un select *from personas
# AGREGAR UNA CAPTURA DE PANTALLA DEL RESULTADO
