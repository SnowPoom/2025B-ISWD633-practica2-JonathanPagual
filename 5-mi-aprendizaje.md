# COMPLETAR  
### Comparando sus conocimientos antes de hacer la práctica con sus conocimientos después de hacer la tarea, explicar los principales aprendizajes logrados para beneficio de su formación profesional.  Si solucionó un problema presentado al realizar la práctica también se debe documentar.

Durante esta práctica se presentó el problema de crear y conectar una base de datos con su interfaz gráfica. El principal inconveniente fue no hacer visibles los puertos de PostgreSQL; sin embargo, al finalizar, se logró realizar esta conexión mediante la configuración de una red donde se encontraban el servidor y el cliente.
Posteriormente, en el segundo ejercicio, se consiguió la configuración de WordPress mediante la revisión de la documentación, ya que en ella se detallan todas las variables de entorno necesarias para crear exitosamente la conexión y el contenedor.
## Consultar: Cómo se gestionan datos confidenciales con los secretos de Docker (Docker Secrets).
Los Docker Secrets son una forma integrada en Docker para almacenar y distribuir datos sensibles a los contenedores sin incluirlos en la imagen, el código, o las variables de entorno visibles y están disponibles principalmente cuando usas Docker Swarm Mode (no en contenedores standalone).
1. se crea el secreto
```
echo "mi-clave-super-secreta" | docker secret create api_key
docker secret create db_password ./password.txt

```
2. se utiliza el secreto
```
docker service create \
  --name mi_servicio \
  --secret api_key \
  alpine cat /run/secrets/api_key
cat /run/secrets/api_key
```
