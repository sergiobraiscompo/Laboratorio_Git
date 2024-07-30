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
![1-Comenzando documentacion](<1-Comenzando documentacion.png>)

# 2. Subiendo el repositorio a github
- Crea un nuevo repositorio en GitHub.
![2-Boton nuevo repo](<2-Boton nuevo repo.png>)
![3-Nombrando repo](<3-Nombrando repo.png>)



- Copia el URL del repositorio que acabas de crear en GitHub
![alt text](4-Copiando%20enlace%20repo.png)
- Conecta tu repositorio local con el repositorio en GitHub.
```
$ git remote add origin git@github.com:sergiobraiscompo/Laboratorio_Git.git
$ git add .
$ git commit -am "Primera push"
    [master (root-commit) 28bafb0] Primera push
    5 files changed, 36 insertions(+)
    create mode 100644 1-Comenzando documentacion.png
    create mode 100644 2-Boton nuevo repo.png
    create mode 100644 3-Nombramos el repo.png
    create mode 100644 4-Copiando enlace repo.png
    create mode 100644 readme.md
```
# 
```
$ exec ssh-agent bash
$ ssh-add ~/.ssh/github
    Identity added: /c/Users/sergi/.ssh/github (github)
```

# Compruebo que puedo realizar una conexión a github
```
$ ssh git@github.com
    PTY allocation request failed on channel 0
    Hi sergiobraiscompo! You've successfully authenticated, but GitHub does not provide shell access.
    Connection to github.com closed.

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
```

# Verifica que la conexión se haya establecido correctamente.
![5-Comprobando repo](<5-Comprobando repo.png>)

# Creción y cambio a la rama "development" 
```
$ git checkout -B development
    Switched to a new branch 'development'
    M       readme.md
```

# Cambio el contenido del archivo readme
![6-Cambios en readme.md](<6-Cambios en readme.md .png>)

# Adición y commit de los cambios realizados en la rama "development".
```
$ git add  .
$ git commit -am "Primer push en la rama 'development'"
    [development ad914ea] Primer push en la rama 'development'
    3 files changed, 67 insertions(+), 2 deletions(-)
    create mode 100644 5-Comprobando repo.png
    create mode 100644 6-Cambios en el readme.png
```

# Push de los cambios a la nueva rama
```
$ git push --set-upstream origin development
    Enumerating objects: 7, done.
    Counting objects: 100% (7/7), done.
    Delta compression using up to 16 threads
    Compressing objects: 100% (5/5), done.
    Writing objects: 100% (5/5), 282.51 KiB | 1.82 MiB/s, done.
    Total 5 (delta 1), reused 0 (delta 0), pack-reused 0
    remote: Resolving deltas: 100% (1/1), completed with 1 local object.
    remote:
    remote: Create a pull request for 'development' on GitHub by visiting:
    remote: https://github.com/sergiobraiscompo/Laboratorio_Git/pull/new/development
    remote: To github.com:sergiobraiscompo/Laboratorio_Git.git
    * [new branch]      development -> development
    branch 'development' set up to track 'origin/development'.
```

## **Hacer un merge**

- Vuelve a la rama "main".
```
$ git checkout main
Switched to branch 'main'
M       readme.md
```

- Haz un merge de la rama "development" a la rama "main".
- Si no hay conflictos, los cambios realizados en la rama "development" se incorporarán a la rama "main".
- Hax un push de los cambios al repositorio en GitHub.

> La rama principal de nuestro repositorio puede ser "main" o "master" según la hayamos nombrado.
>