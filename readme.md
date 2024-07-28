# 1. Creando repo en local
1.1 -  En primer lugar he creado una carpeta en local llamada "0-GITHUB" y entro en ella.

```
mkdir 0-GITHUB
cd 0-GITHUB
```

# Inicio el repo de Git
```
git init
Initialized empty Git repository in C:/Users/sergi/Documents/bootcamp lemoncode/0-GITHUB/.git/
```

# Creo un archivo Markdown llamado readme
```
touch readme\.md
```

## Abro visual studio code en la carpeta actual
code .

## Aquí comienzo la documentación
![alt text](<1-Comenzando documentacion.png>)

# 2. Subiendo el repositorio a github
- Crea un nuevo repositorio en GitHub.
![alt text](<2-Boton nuevo repo.png>)
![alt text](<3-Nombramos el repo.png>)



- Copia el URL del repositorio que acabas de crear en GitHub
![alt text](4-Copiando%20enlace%20repo.png)
- Conecta tu repositorio local con el repositorio en GitHub.
sergi@DESKTOP-64M1J3C MINGW64 ~/Documents/bootcamp lemoncode/0-GITHUB (master)
$ git remote add origin git@github.com:sergiobraiscompo/Laboratorio_Git.git

sergi@DESKTOP-64M1J3C MINGW64 ~/Documents/bootcamp lemoncode/0-GITHUB (master)
$ git add .

sergi@DESKTOP-64M1J3C MINGW64 ~/Documents/bootcamp lemoncode/0-GITHUB (master)
$ git commit -am "Primera push"
[master (root-commit) 28bafb0] Primera push
 5 files changed, 36 insertions(+)
 create mode 100644 1-Comenzando documentacion.png
 create mode 100644 2-Boton nuevo repo.png
 create mode 100644 3-Nombramos el repo.png
 create mode 100644 4-Copiando enlace repo.png
 create mode 100644 readme.md

# Recibo un error de conexión al intentar subir los archivos al repo
sergi@DESKTOP-64M1J3C MINGW64 ~/Documents/bootcamp lemoncode/0-GITHUB (master)
$ git push -u origin master
git@github.com: Permission denied (publickey).
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.

sergi@DESKTOP-64M1J3C MINGW64 ~/Documents/bootcamp lemoncode/0-GITHUB (master)
$ exec ssh-agent bash

sergi@DESKTOP-64M1J3C MINGW64 ~/Documents/bootcamp lemoncode/0-GITHUB (master)
$ ssh-add ~/.ssh/github
Identity added: /c/Users/sergi/.ssh/github (github)

# Compruebo que puedo realizar una conexión a github
sergi@DESKTOP-64M1J3C MINGW64 ~/Documents/bootcamp lemoncode/0-GITHUB (master)
$ ssh git@github.com
PTY allocation request failed on channel 0
Hi sergiobraiscompo! You've successfully authenticated, but GitHub does not provide shell access.
Connection to github.com closed.


sergi@DESKTOP-64M1J3C MINGW64 ~/Documents/bootcamp lemoncode/0-GITHUB (master)
$ git push -u origin master
Enumerating objects: 7, done.
Counting objects: 100% (7/7), done.
Delta compression using up to 16 threads
Compressing objects: 100% (7/7), done.
Writing objects: 100% (7/7), 242.93 KiB | 2.27 MiB/s, done.
Total 7 (delta 0), reused 0 (delta 0), pack-reused 0
To github.com:sergiobraiscompo/Laboratorio_Git.git
 * [new branch]      master -> master
branch 'master' set up to track 'origin/master'.

- Verifica que la conexión se haya establecido correctamente.
![alt text](<5-Comprobando repo.png>)

# Creción y cambio a la rama "development" 
```
git checkout -B development
Switched to a new branch 'development'
M       readme.md
```

- Realiza algunos cambios en el archivo que creaste.
![alt text](6-Cambios%20en%20el%20readme.png)
- Añade y haz un commit con los cambios en la rama "development".
- Sube los cambios a Github.