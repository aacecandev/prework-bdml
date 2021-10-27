---
title: Git cheat sheet
description: git cheat sheet
weight: 60
---
<img src="https://api.brandy.run/core/logo" width="80"/>

# CORE Code School

# Git cheat sheet

- `git init`: Inicializa un repositorio git
- `git status`: estado de los cambios
- `git add <nombre_archivo>`: cambios de fichero a stage
- `git add .`: cambios de todos los ficheros a stage
- `git commit -am "<mensaje>"`: empaquetado de archivos en un commmit añadiendo un mensaje personalizado.
- `git diff`: comparación cambios actuales y último commit
- `git reset HEAD <nombre_archivo>`: eliminar archivo del stage
- `git log`: lista de cambios de nuestro proyecto
- `git checkout -b <nombre_rama>`: Crea una nueva rama (sale en github si haces `git push origin <nombre_rama`)
- `git checkout <nombre_rama>`: Cambia de rama
- `git checkout <commit_id>`: retorno al commit indicado
- `git checkout .`: retorno al commit anterior
- `git remote -v`: Ver a que repositorios remotos esta vinculado este repo
- `git remote set-url origin git://new.url.here`: change the remote Git repository URL
- `git remote remove origin`: remove the remote Git repository URL
- `git checkout -b new_branch`: init new branch before existing repo pull
- `git log --graph --all`: Ver las ramas como un gráfico

### Comandos repositorio remoto

- `git push origin master`: Sube la rama master a git
- `git pull origin master`: Descarga la rama master a git
- `git merge <rama>`: Trae los cambios de `<rama>` a la rama actual
