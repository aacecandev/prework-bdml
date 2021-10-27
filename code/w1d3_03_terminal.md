---
title: Terminal
description: Comandos terminal
weight: 50
---
<img src="https://api.brandy.run/core/logo" width="80"/>

# CORE Code School

# Terminal

Interfaz de texto en nuestro SO para introducir instrucciones. Lo emplearemos principalmente para evitar dependencias y así obtener rápidas respuestas sobre nuestras consultas.

> Consejo: Podemos configurar Visual Studio Code para que sea nuestro editor de código desde la terminal. Para ello, debemos abrir VSC y pulsar `command + p` y escribir en la barra de búsqueda `> install code commmand in PATH` y seleccionar.

### prompt

Se conoce como `prompt` el punto de entrada al terminal para introducir comando. En la documentación de internet figura como `$`.

`Path`: Posición actual donde se encuentra nuestro promt.

## Comandos terminal en local

- `pwd`: Ver en que carpeta esta la terminal
- `mkdir`: crea una carpeta vacia
- `cd`: navegar entre directorios
- `ls`: Listar ficheros en el directorio actual
  - `ls -a`: Lista los archivos (incluídos los ocultos)
  - `ls -als`: Lista los ficheros en modo listado
  - `ls -alh`: Lista los ficheros en modo listado con información de tamaño.
  - `ls -alsh`: Lista los ficheros en modo listado y con los tamaños de fichero legibles en `kb/mb/etc.`
- `ls <nombre_carpeta>`: Lista los elementos de la carpeta (sin entrar en ella).
- `cd`: Navegar entre directorios
  - `cd ..`: Sube al directorio padre
  - `cd <nombre_carpeta>`: Ir a la carpeta <nombre_carpeta>
  - `cd ./<nombre_carpeta>`: El ./ señala la propia carpeta en la que nos encontramos (normalmente no se pone).
- `cp -r <nobre_carpeta> <nueva_carpeta>`: copy project
- `touch <nombre_fichero>`: Crea un archivo de texto en blanco
- `code .`: Abre visual studio code en la carpeta actual
- `open .`: Abre la carpeta actual
- `clear`: Limpia la teminal (CMD+K)
- `man <comando>`: Devuelve el manual del comando introducido
- `*`: Selección de todos los tipos de archivo (por ejemplo, seleccionamos todos los archivos tipo png de la carpeta Pictures con `Pictures/*.png`)
- `>` es un comando de `redirección` que vuelca la salida del comando de mayor a menor. Por ejemplo `cat <nombre_archivo_1> > <nombre_archivo_2>`.
- `>>` vuelva la salida del comando pero manteniendo los contenidos anteriores. Por ejemplo `cat <nombre_archivo_1> >> <nombre_archivo_2>`.
- `mv archivo.txt <nombre_carpeta>`: mover archivos
- `mv archivo.txt mi_archivo.txt`: renombrar archivo
- `rm`: Elimina un fichero
  - `rm -rf`: 🚧Elimina una carpeta y sus ficheros🚧
