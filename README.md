
<center>

# 🚀 Guía de Comandos Git y GitHub

</center>
<br>
<br>
<details>
  <summary style="display: flex; align-items: center; cursor: pointer;">
    <h1 style="margin: 0; padding-left: 10px;">Tabla de Contenido</h1>
  </summary>

## - [1. Comandos básicos de navegación](#1-comandos-básicos-de-navegación)
## - [2. Configuración básica de GIT](#2-configuración-básica-de-git)
## - [3. Commit](#3-commit)
## - [4. Versiones y restauraciones](#4-versiones-y-restauraciones)
## - [5. Atajos y configuraciones](#5-atajos-y-configuraciones)
## - [6. Gestión de ramas](#6-gestión-de-ramas)
## - [7. Almacén temporal (Stash)](#7-almacén-temporal-stash)
## - [8. GITHUB](#8-github)
## - [9. GITHUB](#9-github)

</details>
<br>
<br>


# 1. Comandos básicos de navegación

## Versión de GIT

### Muestra la versión de Git instalada actualmente en el sistema.

```bash
git --version
```
```bash
git -v
```

## Comando de ayuda

### Si alguna vez olvidas cómo funciona un comando o necesitas recordar qué parámetros admite, puedes acceder a la documentación integrada de Git:

```bash
git --help
```
```bash
git -h
```
## Mostar ficheros

### Muestra el contenido (archivos y carpetas) de la ubicación en la que te encuentras actualmente.
```bash
ls
```
## Navegar entre ficheros

### Permite navegar hacia un directorio específico escribiendo su nombre o la ruta donde deseas ir.

```bash
cd
```
### Los "dos puntos" en la terminal representan el directorio anterior (o "padre"). Es el equivalente a hacer clic en el botón de "atrás" en el explorador de archivos de tu sistema operativo.

```bash
cd ..
```
## Ruta exacta en la que estas

### Muestra la ruta absoluta (la dirección completa) del directorio en el que te encuentras posicionado actualmente.

```bash
pwd
```
## Crear carpetas

### Por medio de comando se crea carpetas se debe escribir **mkdir** donde se guardara el archivo y entre comillas despues escribir el nombre de la carpeta.

```bash
mkdir "[nombre]"
```
## Eliminar carpetas
### Eliminar solo la carpeta vacia.
```bash
rmdir "[nombre]"
```
### Eliminar la carpeta con todo el contenido dentro.
```bash
rm -rf "[nombre]"
```
## Limpiar consola

### Cuando tenemos la consola con varios codigos o infromacion que no nos interesa y deseamos mantener la consola limpia.

```bash
clear
```

# 2. Configuración básica de GIT

## Configuración de Identidad Global

### Se utiliza para establecer configuraciones que se aplicarán a todos los proyectos que trabajes en tu computadora.

```bash
git config --global
```
## Configuración de Identidad de Usuario

### Esta sección te ayudará a configurar tu nombre de usuario, el cual quedará registrado en cada "commit" que realices en tus proyectos.

```bash
git config --global user.name "[nombre]"
```
## Configuración de Correo Electrónico

### Define el correo electrónico que se asociará a tu usuario. Es vital para que plataformas como GitHub o GitLab vinculen tus cambios con tu cuenta personal y envíen las notificaciones correspondientes.

```bash
git config --global user.email "[correo]"
```
## Inicializar el repositorio
### Crea el entorno de control de versiones.

```bash
git init
```
## Renombrar Rama
### Este comando es específico para cambiar el nombre de tu rama. Es el paso necesario para alinearte con el estándar actual de los repositorios.

```bash
git branch -m [Nombre]
```
## El Monitor de Estado
### Es el comando que debes ejecutar antes de cualquier acción importante. Te dice qué está pasando en tu carpeta de trabajo y que tiene almacenado GIT.
```bash
git status
```
## Preparar para Guardar
### Este comando mueve tus archivos desde la carpeta de trabajo al "área de preparación" (staging area), dejándolos listos para ser guardados definitivamente en git, solo es colocar el nombre del archivo a guardar.

```bash
git add [Nombre_de_archivo]
```
### Para guardar todos los archivos se necesita el comando

```bash
git add .
```
## Eliminación definitiva del historial y control de versiones de Git
### Se utiliza para destruir el repositorio local de Git asociado a un directorio. Al ejecutarlo, se elimina de forma irreversible el directorio oculto .git.
```bash
rm -rf .git
```

# 3. Commit

## Guardar el Cambio
### Este comando es el que oficializa el registro de los archivos preparados en tu historial. Es como tomar una "foto" permanente de tus cambios.

```bash
git commit -m "[Mensaje descriptivo]"
```
## Lista de cambios
### Este comando es el historial de todo lo que ha ocurrido en tu repositorio. Te permite ver la "lista de fotos" (commits) que has tomado a lo largo del tiempo.

```bash
git log
```
## La de cambios resumida
### Muestra el historial de cambios de forma simplificada, presentando cada commit en una sola línea. Es la mejor herramienta para visualizar rápidamente la secuencia de cambios y obtener los códigos (hashes) necesarios para navegar en el tiempo y sacar el código del commit.
```bash
git log --oneline
```
## Lista de cambios con cambios de cada archivo
### Muestra los cambios realizados en cada archivo si estan eliminados o no
```bash
git log --stat
```
## El Mapa de Ramas
### Genera una representación visual de la estructura y conexión entre tus ramas.
```bash
git log --graph
```
### Genera una representación visual de la estructura y conexión entre tus ramas con el hashes en una linea

```bash
git log --graph --pretty=oneline

```
### Genera una representación visual de la estructura y conexión entre tus ramas con el código en una linea

```bash
git log --graph --decorate --all --oneline

```
## Historial de cambios
### Registra el historial detallado de todos los movimientos que ha realizado el puntero HEAD en tu repositorio. Es la herramienta definitiva de recuperación, ya que permite identificar y restaurar commits que parecen perdidos después de realizar operaciones como [git reset --hard](#restaurar-a-la-ultima-version) o cambios de rama.

```bash
git reflog
```
# 4. Versiones y restauraciones

## Versiones anteriores checkout
### Permite extraer versiones específicas de archivos o estados del proyecto desde el historial. Es ideal para recuperar un archivo antiguo sin alterar el flujo actual de trabajo, solo se necesita tener el código único (hash) que se adquiere con [log](#lista-de-cambios).
### Para un archivo en especifico
```bash
git checkout [hash] --[Nombre_del_archivo]
```
### Para todos los archivos

```bash
git checkout [hash]
```

## Restaurar a la ultima version
### Código permite regresar a la ultima version en la que estas en el "HEAD" y elimina versiones porteriores para verificar todas las versioines posteriores y anteriores puedes usar el comando [reflog](#historial-de-cambios) el cual te permite ver todos los cambios realizados en la rama.

```bash
git reset --hard HEAD
```
## Regresar a version antigua perdiendo lo actual
### Se regresa a la version mas antifua que tu desees pero las versiones posteriores se eliminaran, este mismo codigo te sirve para ir al ultimo commit que tengas solo es buscar el código del commit con [log --oneline](#la-de-cambios-resumida) o con [reflog](#historial-de-cambios)

```bash
git reset --hard [Código]
```

# 5. Atajos y configuraciones avanzadas

## Atajos personalizados con alias
### Permite crear comandos abreviados para tus instrucciones más frecuentes, optimizando tu flujo de trabajo al convertir comandos largos en simples palabras clave.
```bash
git config --global alias.[Nombre] "[Código_de_git_largo]"
```
### Mis comandos optimizados

```bash
git config --global alias.arbol "log --graph --decorate --all --oneline"
git config --global alias.nombre "config --global user.name"
git config --global alias.correo "config --global user.email"
git config --global alias.GCommit "commit -m"
git config --global alias.lista "config --global --list"
git config --global alias.eliminarAlias "config --global --remove-section alias"
git config --global alias.modificarAlias "config --global --edit"
```
## Eliminar atajos personalizados

### Eliminar todos los alias que tengamos
```bash
git config --global --remove-section alias
```
### Modificar o eliminar un alias

```bash
git config --global --edit
```
## Ignorar archivos
### Se debe crear un archivo llamado ".gitignore" y dentro del archivo debe coloar la siguiente:
### "**/[Nombre_del_archivo_a_ignorar]"

## Comparador de Cambios
### Muestra las diferencias exactas entre tus archivos actuales y el último commit (o entre diferentes versiones). Es la herramienta fundamental para revisar qué código has modificado, añadido o eliminado antes de guardarlo en tu historial.

```bash
git diff
```
## Marcadores de Versión
### Permiten asignar nombres o etiquetas permanentes a puntos específicos del historial (como versiones v1.0, v2.0 o hitos importantes). A diferencia de los commits, las etiquetas son puntos de referencia fijos e inamovibles.
```bash
git tag [Nombre]
```
## Viaje a un Hito de tag
### Permite navegar a un punto específico marcado con una etiqueta (tag). Al ejecutarlo, tu proyecto retrocede exactamente al estado en el que se encontraba cuando creaste esa versión, funcionando como un "punto de guardado" histórico.

```bash
git checkout tags/[Nombre_de_tags]
```

# 6. Gestión de ramas

## Listar ramas existentes
### Comando para conocer todas las ramas que tenemos en el sistema

```bash
git branch
```
## Crear una rama nueva
### Se crea una rama a partir del commit en el que te encuentes.

```bash
git branch [Nombre-de-la-nueva-rama]
```
### rear y cambia a la rama que cres
```bash
git switch -c [Nombre-de-la-nueva-rama]
```
## Renombrar la rama actual
### Para renombrar la rama debemos estar en ella y luego digitar el cóidigo

```bash
git branch -m [Nombre-nuevo]
```

## Eliminar una rama
### Si estás 100% seguro de que los cambios en rama no sirven para nada y no te importa perderlos, usa la D mayúscula como te sugiere el propio Git:
```bash
git branch -D [Nombre-de-rama]
```
### Cuando ya se fusiono la rama con la principal y no necesitas mas la rama.
```bash
git branch -d [Nombre-de-rama]
```
## Cambiar a una rama existente
### Con este comando puedes navegar entre ramas
```bash
git switch [Nombre-rama]
```
## Fusion de ramas
### Toma el historial de una rama específica y lo fusiona con la rama en la que te encuentras actualmente. Es el proceso estándar para combinar funcionalidades terminadas o corregir errores en la línea de tiempo principal del proyecto.
```bash
git merge [Rama-donde-traeras-los-cambios]
```

# 7. El almacén temporal (Stash)

## El almacén temporal
### Permite guardar tus cambios locales sin hacer un commit, dejando tu área de trabajo limpia. Ideal para cambiar de rama rápidamente y retomar el trabajo después.

```bash
git stash
```
## Recuperar el cambio temporal
### Se recupera el archio temporar para continuar con los cambios

```bash
git stash pop
```

## Lista de archivos temporales
### Se lista todos los archivos temporales que se tienen guardados

```bash
git stash list
```
## Eliminar algun archivo temporal

### Eliminar archivos temporales porque no se necesitan modificar

```bash
git stash drop
```

# 8. Configuración de SSH
## Verificación Llaves SSH Locales
### Es esencial para verificar qué llaves criptográficas (públicas y privadas) tienes generadas y validar que los permisos de seguridad de tus credenciales sean correctos.
```bash
ls -al ~/.ssh
```
## Eliminacion de claves SSH
### Comando de mantenimiento diseñado para eliminar de forma permanente todas las llaves SSH y configuraciones de host almacenadas en el sistema.
```bash
rm -rf ~/.ssh/*
```
## Generar Nueva Llave SSH
### Este comando crea un par de llaves de seguridad para autenticarte en servicios como GitHub o servidores remotos sin usar contraseñas. Se utiliza ed25519 por ser actualmente el método más rápido y seguro para este proceso.
```bash
ssh-keygen -t ed25519 -C "[Correo]"
```
## Iniciar el Agente SSH
### Este comando activa en segundo plano el "agente" de SSH, que es un programa encargado de recordar tus llaves y contraseñas. Gracias a esto, no tienes que escribir tu clave cada vez que te conectas a un servidor o a GitHub durante tu sesión de trabajo.

```bash
eval "$(ssh-agent -s)"
```
## Crear Archivo de Configuración SSH
### Este comando crea un archivo vacío llamado config dentro del directorio .ssh. Este archivo es fundamental para gestionar preferencias de conexión, como asignar nombres cortos a servidores remotos o especificar qué llave usar para cada host, facilitando el acceso automatizado.
```bash
touch ~/.ssh/config
```
## Configuración Automática de Host GitHub
### Define las reglas de conexión específicas para GitHub dentro del archivo de configuración SSH. Permite el uso automático del agente SSH, integra el llavero del sistema para mejorar la seguridad y especifica la llave "id_sdfew" para autenticar el acceso a tus repositorios sin intervención manual constante.

### Mac
```bash
cat <<EOF >> ~/.ssh/config

Host *.github.com
  AddKeysToAgent yes
  UseKeychain yes
  IdentityFile ~/.ssh/[Nombre de fichero de clave publica/privada que inicia con id]
EOF
```
### Windos
```bash
cat > ~/.ssh/config <<EOF
Host *.github.com
  AddKeysToAgent yes
  IdentityFile ~/.ssh/[Nombre de fichero de clave publica/privada que inicia con id]
EOF
```
### Linux
```bash
cat > ~/.ssh/config <<EOF
Host *.github.com
  AddKeysToAgent yes
  IdentityFile ~/.ssh/[Nombre de fichero de clave publica/privada que inicia con id]
EOF
```
## Añadir Llave al Agente SSH
### La informacion paso a paso esta en el [enlace](https://docs.github.com/es/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent?platform=windows)
### En linux
```bash
eval "$(ssh-agent -s)" && ssh-add ~/.ssh/[Nombre de fichero de clave publica/privada que inicia con id]
```
### En Windows
```bash
Start-Service ssh-agent; ssh-add $env:USERPROFILE\.ssh\[Nombre de fichero de clave publica/privada que inicia con id]
```
### En Mac
```bash
ssh-add --apple-use-keychain ~/.ssh/[Nombre de fichero de clave publica/privada que inicia con id]
```
## Sincronización de Autenticación con Agente SSH
### Muestra en pantalla el contenido de tu llave pública SSH. Este texto es el que debes copiar y registrar en la configuración de tu cuenta de GitHub para permitir la autenticación segura desde tu equipo.
```bash
cat ~/.ssh/[Nombre de fichero de clave publica/privada que inicia con id].pub
```
## Verificación de la Conexión SSH
### Este comando realiza una prueba de conexión directa a los servidores de GitHub. Su función es verificar que tu llave SSH esté configurada correctamente y que el servidor pueda autenticar tu identidad exitosamente.
```bash
ssh -T git@github.com
```

# 9. GITHUB

## Vincular un Repositorio Local con un Servidor Remoto
### Es el comando que vincula tu repositorio local con un servidor remoto (como GitHub). Establece una ruta para que puedas subir (push) y bajar (pull) tu código de la nube, guardando esa dirección bajo el nombre por defecto "origin".

```bash
git remote add origin [ENLACE_DE_GITHUB]
``` 

## Vincular y Subir Cambios por Primera Vez
### Es el comando que sube tus archivos locales por primera vez a la rama principal (main) del servidor remoto (origin) y crea un enlace permanente entre ambas ramas.
```bash
git push -u origin main
``` 
## Subir Cambios Locales al Servidor Remoto
### Es el comando estándar para enviar tus confirmaciones (commits) locales al servidor en la nube (como GitHub). Actualiza el repositorio remoto con el código más reciente que tienes en tu computadora.
```bash
git push
``` 
## Descargar el Historial del Servidor Sin Modificar tu Código
### Es el comando que consulta el repositorio remoto para descargar las novedades e historial de commits más recientes, pero sin alterar tus archivos actuales.
```bash
git fetch
``` 

## Descargar y Fusionar Cambios del Servidor de Forma Automática
### es el comando que trae los últimos cambios desde el repositorio remoto y los integra inmediatamente en tus archivos locales.

```bash
git pull
``` 
### Si es la primera vez utilizando este código puede enviarte un error y debes escoger alguno de estos codigo
### El recomendado. Configura Git para que, al usar git pull, combine el código remoto con el tuyo mediante una fusión tradicional (merge). Si los historiales han tomado caminos diferentes, creará automáticamente un commit especial de fusión (merge commit) para unirlos.
```bash
git config pull.rebase false
``` 
### Configura Git para que, al usar git pull, aplique la técnica de rebasar (rebase). En lugar de crear un commit de fusión, Git "despegará" temporalmente tus commits locales, descargará los cambios del servidor y luego volverá a colocar tus commits uno a uno encima del código actualizado, manteniendo un historial completamente lineal y limpio.
```bash
git config pull.rebase true
``` 
### Configura Git para que solo permita hacer git pull si la actualización se puede resolver mediante un avance rápido (fast-forward). Esto significa que solo descargará los cambios si tú no has creado ningún commit nuevo a nivel local; si tienes cambios propios que causen una bifurcación, Git detendrá el proceso de inmediato para que decidas manualmente cómo resolverlo.
```bash
git config pull.ff only
``` 
## Forzar la Subida de Cambios al Servidor Remoto
### Es el comando que sube de forma obligatoria tus archivos locales a la rama principal (main) en la nube, sobrescribiendo por completo lo que haya en el servidor.
```bash
git push -u origin main --force
``` 
## Clonar un Repositorio Remoto en tu Computadora
### es el comando que se utiliza para descargar una copia exacta y completa de un repositorio existente en la nube (como GitHub) hacia tu computadora local.

```bash
git clone [URL de repositorio]
```
<br>
<br>
<center>

# 💡 Este repositorio es una **Base de conocimiento** personal en constante evolución. 
## Si encuentras un error o tienes un comando que consideres útil para optimizar el flujo de trabajo, no dudes en abrir un *Issue* o enviarme una sugerencia. 
# ¡El aprendizaje colaborativo es la base de la ingeniería! 🤝🛠️
</center>
