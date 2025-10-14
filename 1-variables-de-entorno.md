# Variables de Entorno
### ¿Qué son las variables de entorno?

Son valores dinámicos con nombre que influyen en el comportamiento de programas y sistemas al proporcionar información de configuración sin alterar el código fuente. 
### Para crear un contenedor con variables de entorno

```
docker run -d --name <nombre contenedor> -e <nombre variable1>=<valor1> -e <nombre variable2>=<valor2>
```

### Crear un contenedor a partir de la imagen de nginx:alpine con las siguientes variables de entorno: username y role. Para la variable de entorno rol asignar el valor admin.
```
docker run -d --name var-ent -e username=snowpoom -e role=admin nginx:alpine
```
# CAPTURA CON LA COMPROBACIÓN DE LA CREACIÓN DE LAS VARIABLES DE ENTORNO DEL CONTENEDOR ANTERIOR
```
docker inspect var-ent
```
<img width="1100" height="597" alt="image" src="https://github.com/user-attachments/assets/7f3dc0a8-ac7c-4957-9add-9340fb1fdf43" />

### Crear un contenedor con la imagen de mysql, mapear todos los puertos
```
docker run -d --name mysql -P mysql
```
### ¿El contenedor se está ejecutando?
no, se cierra al momento de ejecutar
### Identificar el problema
Se necesita especificar alguna de las 3 variables de entorno que solicita la imagen
### Para crear un contenedor con variables de entorno especificadas
- Portabilidad: Las aplicaciones se vuelven más portátiles y pueden ser desplegadas en diferentes entornos (desarrollo, pruebas, producción) simplemente cambiando el archivo de variables de entorno.
- Centralización: Todas las configuraciones importantes se centralizan en un solo lugar, lo que facilita la gestión y auditoría de las configuraciones.
- Consistencia: Asegura que todos los miembros del equipo de desarrollo o los entornos de despliegue utilicen las mismas configuraciones.
- Evitar Exposición en el Código: Mantener variables sensibles como contraseñas, claves API, y tokens fuera del código fuente reduce el riesgo de exposición accidental a través del control de versiones.
- Control de Acceso: Los archivos de variables de entorno pueden ser gestionados con permisos específicos, limitando quién puede ver o modificar la configuración sensible.

### Crear un contenedor con mysql, mapear todos los puertos y configurar las variables de entorno mediante un archivo

# CAPTURA CON LA COMPROBACIÓN DE LA CREACIÓN DE LAS VARIABLES DE ENTORNO DEL CONTENEDOR ANTERIOR 
<img width="1002" height="252" alt="image" src="https://github.com/user-attachments/assets/0fc96580-e8ab-47ba-b934-ba04cc42c178" />

### ¿Qué bases de datos existen en el contenedor creado?
existen 4 bases de datos
<img width="1099" height="666" alt="image" src="https://github.com/user-attachments/assets/cbaa148f-a236-43dc-ae9b-ef1e2673a0d1" />


