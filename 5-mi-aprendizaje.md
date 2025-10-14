# COMPLETAR  
Comparando sus conocimientos antes de hacer la práctica con sus conocimientos después de hacer la tarea, explicar los principales aprendizajes logrados para beneficio de su formación profesional.  
Si solucionó un problema presentado al realizar la práctica también se debe documentar.

Consultar: Cómo se gestionan datos confidenciales con los secretos de Docker (Docker Secrets).
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
