# UNIX Apuntes

## Comandos Básicos

- `>`: Redirecciona la salida a un archivo.
- `>>`: Añade la salida a un archivo existente.
- `cat`: Muestra el contenido de un archivo. Ejemplo: `cat archivo.txt`.
- `echo`: Muestra texto por pantalla. Ejemplo: `echo "Hola Mundo"`.
- `tee`: Guarda la salida en un archivo y la muestra por pantalla. Ejemplo: `ls | tee lista.txt`.
- `more`: Muestra el contenido de un archivo página por página.
- `less`: Permite navegar hacia arriba y abajo en un archivo.
- `ls`: Lista archivos y directorios en la ubicación actual.
- `cd`: Cambia de directorio.
- `pwd`: Muestra el directorio actual.
- `mkdir`: Crea un directorio.
- `rm`: Elimina archivos o directorios.
- `cp`: Copia archivos o directorios.
- `mv`: Mueve o renombra archivos.
- `ps`: Muestra procesos en ejecución. Ejemplo: `ps aux`.
- `kill`: Termina un proceso.
- `top`: Muestra procesos en tiempo real.
- `jobs`: Lista procesos en segundo plano.
- `bg`: Envía un proceso suspendido a segundo plano. Ejemplo: `bg %1`.
- `fg`: Trae un proceso al primer plano.
- `nano`: Editor de texto básico.
- `vi`: Editor de texto avanzado.
- `touch`: Crea un archivo vacío o actualiza su fecha de modificación.
- `grep`: Busca patrones en archivos. Ejemplo: `grep "error" archivo.txt`.
- `find`: Busca archivos en el sistema.
- `chmod`: Cambia los permisos de un archivo.
- `chown`: Cambia el propietario de un archivo.
- `su`: Cambia de usuario. Ejemplo: `su root`.
- `sudo`: Ejecuta comandos con permisos de administrador.
- `locate`: Busca archivos en el sistema.
- `sudo su`: Cambia a usuario administrador.

## Permisos

- `r`: Lectura (4)
- `w`: Escritura (2)
- `x`: Ejecución (1)

Ejemplo de permisos:
- `chmod 755 archivo.txt`: Da permisos de lectura, escritura y ejecución al dueño, y solo lectura a los demás.
- `chmod u+w archivo.txt`: Agrega permiso de escritura al dueño.
- `chmod o-r archivo.txt`: Quita permisos de lectura a otros.

## Gestión de Usuarios

- `useradd`: Crea un nuevo usuario.
- `passwd`: Cambia la contraseña de un usuario.
- `/etc/passwd`: Información de usuarios del sistema.
- `/etc/shadow`: Información de contraseñas encriptadas.

## Red y Conexiones

- `iptables`: Configura reglas de firewall.
- `ssh`: Conexión remota a servidores.

## Ejemplos Prácticos

### Crear y Editar Archivos

```bash
touch archivo.txt
nano archivo.txt
cat archivo.txt


