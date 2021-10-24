GIT

GIT INIT (inicial de git)
GIT ADD BIOGRAFICA.TXT (GIT ADD . (TODOS LOS CAMBIOS))
GIT COMMIT -M "primera version" (sube la primera versión del archivo)
(cambios)
GIT ADD .
GIT COMMIT -M "segunda versión"
GIT STATUS (ESTATUS DE CADA ARCHIVO)
GIT SHOW

GIT LOG BIOGRAFICA.TXT (HISTORIAL DE CAMBIOS DE UN ARCHIVO)
GIT PUSH (ENVIAR HACIA OTRO SERVIDOR REMOTO)
GIT PULL (TRAER ARCHIVO DE UN SERVIDOR REMOTO)


GIT --VERSION  (VER LA VERSION EXACTA QUE TENEMOS INSTALADA)
GIT CONFIG --LIST (toda la lista de valores que tenemos en esta maquina)
GIT CONFIG --GLOBAL USER.NAME "OSCARDO"
GIT CONFIG --GLOBAL USER.EMAIL "OSCARDO2000@GMAIL.COM"

git diff ad39c7dbbda45678e1b0300347515dda0f56ade7 4bda7c5ce90d20051002d9914f0b3cd7a8000126 (diferencias entre versiones)

git reset ad39c7dbbda45678e1b0300347515dda0f56ade7 --hard (nos permite volver en el tiempo de nuestro archivo)  
git reset ad39c7dbbda45678e1b0300347515dda0f56ade7 --soft 

--hard (TODO vuelve a nuestro archivo anterior) o --soft (casi todo vuelve a nuestra versión anterior PERO debemos hacerle commit)

git log --stat (ver todos los cambios de que han hecho en los archivos)

GIT CHECKOUT |MASTER || ...a0f56ade7 | archivo.txt 

GIT RESET O GIT RM

GIT CLONE URL (clonar una url que sea donde vamos a subir los documentos)
GIT PUSH (LLEVAR DE NUESTR EQUIPO LOCAL A LA NUBE O INTERNET)
GIT FETCH (TRAER DE NUESTRA NUBE O INTERNET A NUESTRO EQUIPO LOCAL)
	GIT MERGE (UNE LA INFORMACION QUE TENEMOS EN LA NUBE CON NUESTRO EQUIPO LOCAL Y LOS FUSIONA)
	O
	GIT PULL (UNIÓN ENTRE GIT FETCH y GIT MERGE)
	
git branch xxxxxxxxx (rama o branch para determinar los distintos nombre)
git checkout xxxxxxx (cambio de rama a rama)
git merge (rama que desea copiar) "mensaje a mostrar"

git checkout master
(master) git merge cabecera "mensaje a mostrar"

ADICIONAR UN REPOSITORIO REMOTO 

git remote add origin https://github.com/oscardo/cursogithub.git

git remote 
	origin

git remote -v
origin  https://github.com/oscardo/cursogithub.git (fetch --> descargar los archivos)
origin  https://github.com/oscardo/cursogithub.git (push ---> cargar los archivos)

git push origin master

$ git config --global user.email "oscardo2000@gmail.com"
$ ssh-keygen -t rsa -b 4096 -C "oscardo2000@gmail.com"
$ git log --all --graph --decorate --oneline
alias arbolito="git log --all --graph --decorate --oneline"
$ git tag -a v0.1 -m "resultado de desarrollo" 725e1ef
gitk

git push origin cabecera



 creamos otra rama 
 git branch fix-type
 hacemos los cambios que necesitamos realizar
 git push origin fix-type --y subimos los cambios a origin (web) con nuestro cambio con nuestra rama local
 
 
COMANDOS ÚTILES PARA GIT
1. Git clone
 git clone <https://link-con-nombre-del-repositorio>
2. Git branch
 Creando una nueva rama:
  git branch <nombre-de-la-rama>
 Este comando creará una rama en local. Para enviar (push) la nueva rama al repositorio remoto, necesitarás usar el siguiente comando
  git push <nombre-remoto> <nombre-rama>
 Visualización de ramas:
  git branch
  git branch --list
 Borrar una rama:
  git branch -d <nombre-de-la-rama>
3. Git checkout
 git checkout <nombre-de-la-rama>
Hay también un comando de acceso directo que te permite crear y cambiarte a esa rama al mismo tiempo:
 git checkout -b <nombre-de-tu-rama> 
Este comando crea una nueva rama en local (-b viene de rama (branch)) y te cambia a la rama que acabas de crear.
4. Git status
El comando de git status nos da toda la información necesaria sobre la rama actual.
 git status	
5. Git add
 git add <archivo>
 git add -A
6. Git commit
 git commit -m "mensaje de confirmación"
7. Git push
Después de haber confirmado tus cambios, el siguiente paso que quieres dar es enviar tus cambios al servidor remoto. Git push envía tus commits al repositorio remoto.
 git push <nombre-remoto> <nombre-de-tu-rama>
De todas formas, si tu rama ha sido creada recientemente, puede que tengas que cargar y subir tu rama con el siguiente comando:
 git push --set-upstream <nombre-remoto> <nombre-de-tu-rama>
or 
 git push -u origin <nombre-de-tu-rama>
Importante: Git push solamente carga los cambios que han sido confirmados.

8. Git pull
El comando git pull se utiliza para recibir actualizaciones del repositorio remoto. Este comando es una combinación del git fetch y del git merge lo cual significa que cundo usemos el git pull recogeremos actualizaciones del repositorio remoto (git fetch) e inmediatamente aplicamos estos últimos cambios en local (git merge).
 git pull <nombre-remoto>
9. Git revert
 git revert 3321844
Después de esto, verás una pantalla como la de abajo -tan solo presiona shift + q para salir:
10. Git merge
 Primero, debes cambiarte a la rama dev:
	git checkout dev
Antes de fusionar, debes actualizar tu rama dev local:
    git fetch
Por último, puedes fusionar tu rama de características en la rama dev:
	git merge <nombre-de-la-rama>
Pista: Asegúrate de que tu rama dev tiene la última versión antes de fusionar otras ramas, si no, te enfrentarás a conflictos u otros problemas no deseados.