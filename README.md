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

---

## Permisos

- `r`: Lectura (4)
- `w`: Escritura (2)
- `x`: Ejecución (1)

Ejemplo de permisos:
- `chmod 755 archivo.txt`: Da permisos de lectura, escritura y ejecución al dueño, y solo lectura a los demás.
- `chmod u+w archivo.txt`: Agrega permiso de escritura al dueño.
- `chmod o-r archivo.txt`: Quita permisos de lectura a otros.

---

## Gestión de Usuarios

- `useradd`: Crea un nuevo usuario.
- `passwd`: Cambia la contraseña de un usuario.
- `/etc/passwd`: Información de usuarios del sistema.
- `/etc/shadow`: Información de contraseñas encriptadas.

---

## Red y Conexiones

- `iptables`: Configura reglas de firewall.
- `ssh`: Conexión remota a servidores.

---

## Ejemplos Prácticos

### Crear y Editar Archivos

- `touch archivo.txt`: Crea un archivo vacío.
- `nano archivo.txt`: Abre el archivo en el editor Nano.
- `cat archivo.txt`: Muestra el contenido del archivo.

### Crear un Archivo con Texto

- `echo "Este es un texto" > archivo.txt`: Crea un archivo con texto.

### Ver Archivos Grandes

- `more archivo-grande.txt`: Muestra el contenido de un archivo grande página por página.
- `less archivo-grande.txt`: Permite navegar hacia arriba y abajo en un archivo grande.

### Ordenar Archivos

- `sort nombres.txt`: Ordena un archivo alfabéticamente.
- `sort -n edades.txt`: Ordena un archivo numéricamente.
- `sort -k2 nombres_y_edades.txt`: Ordena por la segunda columna.
- `sort -r nombres.txt`: Ordena en reversa.
- `sort -u`: Elimina duplicados.

### Buscar Archivos

- `find /home -name "*.txt"`: Busca archivos por nombre.
- `find /var -size +10M`: Busca archivos mayores de 10MB.
- `find . -type d`: Busca directorios en la carpeta actual.

### Gestión de Procesos

- `ps`: Muestra procesos actuales.
- `ps aux`: Muestra procesos con detalles.
- `ps -u usuario`: Muestra procesos por usuario.
- `top`: Muestra procesos en tiempo real.
- `kill PID`: Termina un proceso.
- `kill -9 PID`: Termina un proceso de manera forzosa.
- `jobs`: Lista procesos en segundo plano.
- `fg %1`: Trae un proceso al primer plano.
- `bg %1`: Envía un proceso a segundo plano.

### Enlaces Simbólicos y Duros

- **Enlace duro**: Apunta directamente al archivo en el disco. Si el archivo original se elimina, el enlace sigue funcionando.
- **Enlace simbólico**: Similar a un acceso directo. Si el archivo original se elimina, el enlace deja de funcionar.

- `ln -s /ruta/origen.txt enlace_simbolico`: Crea un enlace simbólico.
- `ln origen.txt enlace_duro`: Crea un enlace duro.

### Ejemplo de Enlaces

- `touch origen.txt`: Crea un archivo.
- `ln origen.txt enlace_hard`: Crea un enlace duro.
- `ln -s origen.txt enlace_soft`: Crea un enlace simbólico.
- `cat enlace_hard`: Muestra el contenido del enlace duro.
- `cat enlace_soft`: Muestra el contenido del enlace simbólico.
- `rm origen.txt`: Elimina el archivo original.
- `cat enlace_hard`: Sigue funcionando.
- `cat enlace_soft`: Deja de funcionar.

### Eliminar Archivos Antiguos

- `find /var/log -type f -mtime +30 -exec rm {} \;`: Elimina archivos con más de 30 días.

### Cambiar Propietario de Archivos

- `chown usuario:grupo archivo.txt`: Cambia el propietario de un archivo.
- `sudo chown root archivo.txt`: Cambia el dueño a root.

### Instalar Programas

- `sudo apt update`: Actualiza la lista de paquetes.
- `sudo apt install tree`: Instala el programa 'tree'.

### Ver Estructura de Directorios

- `ls /`: Muestra la estructura del directorio raíz.
- `tree /`: Muestra la estructura en forma de árbol.

### Tipos de Archivos

- **Archivos regulares**: Texto o binarios.
- **Directorios**: Carpetas que contienen archivos.
- **Enlaces**: Punteros a otros archivos (duros o simbólicos).
- **Especiales**: Dispositivos del sistema.

### Ver Tipo de Archivo

- `file /etc/passwd`: Muestra el tipo de archivo.

### Crear y Eliminar Usuarios

- `sudo useradd nombre_usuario`: Crea un nuevo usuario.
- `sudo passwd nombre_usuario`: Cambia la contraseña de un usuario.
- `sudo userdel -r nombre_usuario`: Elimina un usuario y su directorio.

### Ver Lista de Usuarios

- `cat /etc/passwd`: Muestra la lista de usuarios.

### Ejemplo de Script

- `echo "echo 'Buenos días'" > script.sh`: Crea un script.
- `echo "ls" >> script.sh`: Añade un comando al script.
- `bash script.sh > salida.txt 2> errores.txt`: Ejecuta el script y separa salidas.
- `cat salida.txt`: Muestra la salida estándar.
- `cat errores.txt`: Muestra los errores.

### Ordenar y Filtrar Archivos

- `sort archivo.txt > archivo_ordenado.txt`: Ordena un archivo.
- `grep "ERROR" logs.txt > errores.txt`: Filtra líneas con "ERROR".
- `sort -u archivo.txt > archivo_unico.txt`: Elimina líneas duplicadas.

### Ver Archivos Grandes

- `find /home -size +1M`: Busca archivos mayores de 1MB.

### Crear Archivo de Registro de Procesos

- `ps aux > procesos.txt`: Crea un archivo de registro de procesos.

### Copiar Directorios

- `cp -r directorio1/ directorio2/`: Copia directorios.

### Eliminar Directorios

- `rm -r directorio/`: Elimina directorios.

### Mover Varios Archivos

- `mv /ruta/origen/*.txt /ruta/destino/`: Mueve varios archivos.

### Dar Permisos a Varios Archivos

- `chown -R usuario:grupo /ruta/directorio/`: Cambia el propietario de varios archivos.


