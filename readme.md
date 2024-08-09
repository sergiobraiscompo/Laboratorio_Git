### Creando repo en local
En primer lugar he creado una carpeta en local llamada "0-GITHUB" y entro en ella.

```
mkdir 0-GITHUB
cd 0-GITHUB
```

### Inicio el repo de Git
```
git init
    Initialized empty Git repository in C:/Users/sergi/Documents/bootcamp lemoncode/0-GITHUB/.git/
```


### Creo un repo en remoto y copio la url del mismo para enlazarlo en local
![boton nuevo repo](<images/2-Boton nuevo repo.png>)
![nombrando repo](<images/3-Nombrando repo.png>)
![copiando url](<images/4-Copiando enlace repo.png>)

### Creo un par de llaves pública-privada y añado la clave pública a la cuenta de github
```
cd ~/.ssh/
ssh-keygen -t rsa -b 4096 -C "mail@gmail.com"
    Generating public/private rsa key pair.
    Enter file in which to save the key (/c/Users/User/.ssh/id_rsa): github
    Enter passphrase (empty for no passphrase):
    Enter same passphrase again:
    Your identification has been saved in github
    Your public key has been saved in github.pub
    The key fingerprint is:
    SHA256:
    mail@gmail.com
    The key's randomart image is:
    +---[RSA 4096]----+
    |            .E   |
    |       . .  o.o  |
    |        o +o.O   |
    |       . + o+ *  |
    |       .S o..=.  |
    |    . . ..o==... |
    | o   o o  ==.oo .|
    |..o ....o. +oo o |
    |  o+. . o+oo+   o|
    +----[SHA256]-----+

```
![subiendo clave pública](<images/4.1-Copiando clave a github.png>)

### Añado la key a mi host local y compruebo la conexión
```
$ exec ssh-agent bash
$ ssh-add ~/.ssh/github
    Identity added: /c/Users/sergi/.ssh/github (github)
$ ssh git@github.com
    PTY allocation request failed on channel 0
    Hi sergiobraiscompo! You've successfully authenticated, but GitHub does not provide shell access.
    Connection to github.com closed.
```

### Creo un archivo Markdown llamado readme
```
touch readme\.md
```

### Abro visual studio code en la carpeta actual
code .

### Empiezo a documentar los pasos que sigo
![comenzando documentacion](<images/1-Comenzando documentacion.png>)

### Compruebo que puedo realizar una conexión a github y hago un push de los cambios realizados
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

### Compruebo que la push se ha realizado correctamente
![5-Comprobando repo](<images/5-Comprobando repo.png>)

# Creción y cambio a la rama "development" 
```
$ git checkout -B development
    Switched to a new branch 'development'
    M       readme.md
```

### Cambio el contenido del archivo readme
![6-Cambios en readme.md](<images/6-Cambios en readme.md.png>)

### Adición y commit de los cambios realizados en la rama "development".
```
$ git add  .
$ git commit -am "Primer push en la rama 'development'"
    [development ad914ea] Primer push en la rama 'development'
    3 files changed, 67 insertions(+), 2 deletions(-)
    create mode 100644 5-Comprobando repo.png
    create mode 100644 6-Cambios en el readme.png
```

### Push de los cambios a la nueva rama
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

### Después realizo el "mergeo" y subo los cambios a github
```
$ git checkout master
    Switched to branch 'master'
    Your branch is up to date with 'origin/master'.
$ git merge development
    Updating 28bafb0..e42f007
    Fast-forward
    3-Nombramos el repo.png => 3-Nombrando repo.png | Bin
    5-Comprobando repo.png                          | Bin 0 -> 68334 bytes
    6-Cambios en readme.md .png                     | Bin 0 -> 259096 bytes
    7-Notificacion github.png                       | Bin 0 -> 17930 bytes
    readme.md                                       | 105 ++++++++++++++++++++++--
    5 files changed, 99 insertions(+), 6 deletions(-)
    rename 3-Nombramos el repo.png => 3-Nombrando repo.png (100%)
    create mode 100644 5-Comprobando repo.png
    create mode 100644 6-Cambios en readme.md .png
    create mode 100644 7-Notificacion github.png
$ git add .
$ git commit -am "Fusión con la rama development"
    On branch master
    Your branch is ahead of 'origin/master' by 6 commits.
    (use "git push" to publish your local commits)
$ git push
    Enumerating objects: 5, done.
    Counting objects: 100% (5/5), done.
    Delta compression using up to 16 threads
    Compressing objects: 100% (3/3), done.
    Writing objects: 100% (3/3), 683 bytes | 683.00 KiB/s, done.
    Total 3 (delta 2), reused 0 (delta 0), pack-reused 0
    remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
    To github.com:sergiobraiscompo/Laboratorio_Git.git
```

![alt text](<images/7-Notificacion github.png>)
![alt text](<images/8-mergeado subido a github.png>)