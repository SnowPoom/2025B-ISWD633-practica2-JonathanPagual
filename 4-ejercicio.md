## Esquema para el ejercicio
![Imagen](esquema-4-ejercicio.PNG)

### Crear la red
```
docker network create net-wp -d bridge
```
### Crear el contenedor mysql a partir de la imagen mysql:8, configurar las variables de entorno necesarias
```
docker run --name cont-mysql -e MYSQL_ROOT_PASSWORD=snowpoom -d mysql:8
```
### Crear el contenedor wordpress a partir de la imagen: wordpress, configurar las variables de entorno necesarias
```
docker run -d --name cont-wordpress --network net-wp -p 8787:80 -e WORDPRESS_DB_HOST=cont-mysql -e WORDPRESS_DB_USER=root -e WORDPRESS_DB_PASSWORD=snowpoom -e WORDPRESS_DB_NAME=mysql wordpress
```
De acuerdo con el trabajo realizado, en el esquema del ejercicio el puerto a es 8787

Ingresar desde el navegador al wordpress y finalizar la configuración de instalación.
# COLOCAR UNA CAPTURA DE LA CONFIGURACIÓN
<img width="1102" height="871" alt="image" src="https://github.com/user-attachments/assets/a0875461-371a-454c-ab32-6fe627828fe4" />


Desde el panel de admin: cambiar el tema y crear una nueva publicación.
Ingresar a: http://localhost:9300/ 
recordar que a es el puerto que usó para el mapeo con wordpress
# COLOCAR UNA CAPTURA DEL SITO EN DONDE SEA VISIBLE LA PUBLICACIÓN.
<img width="1899" height="859" alt="image" src="https://github.com/user-attachments/assets/77ed10b9-5311-4268-96fb-20672d6dd0e2" />

### Eliminar el contenedor wordpress
```
docker rm -f cont-wordpress
```
### Crear nuevamente el contenedor wordpress
Ingresar a: http://localhost:9300/ 
recordar que a es el puerto que usó para el mapeo con wordpress

### ¿Qué ha sucedido, qué puede observar?
No me solicitó configurar de nuevo el sitio web de wordpress, se cargó directamente el sitio web creado anteriormente puede deberse a la base de datos ya que esta no fue eliminada.
