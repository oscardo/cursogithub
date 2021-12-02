GIT PRIMEROS PASOS DE ESTO!!!
- - -
git init (inicial de git)
- - -
git add biografica.txt (git add . (todos los cambios))
- - -
git commit -m "primera version" (sube la primera versión del archivo)
(cambios)
- - -
git add .
- - -
git commit -m "segunda versión"
- - -
git status (estatus de cada archivo)
- - -
git show
* * *
git log biografica.txt (historial de cambios de un archivo)
- - -
git push (enviar hacia otro servidor remoto)
- - -
git pull (traer archivo de un servidor remoto)
- - -
* * *
git --version  (ver la version exacta que tenemos instalada)
- - -
git config --list (toda la lista de valores que tenemos en esta maquina)
- - -
git config --global user.name "oscardo"
- - -
git config --global user.email "oscardo2000@gmail.com"
- - -
git diff ad39c7dbbda45678e1b0300347515dda0f56ade7 4bda7c5ce90d20051002d9914f0b3cd7a8000126 (diferencias entre versiones)
- - -
git reset ad39c7dbbda45678e1b0300347515dda0f56ade7 --hard (nos permite volver en el tiempo de nuestro archivo)  
- - -
git reset ad39c7dbbda45678e1b0300347515dda0f56ade7 --soft 
- - -
--hard (todo vuelve a nuestro archivo anterior) o --soft (casi todo vuelve a nuestra versión anterior pero debemos hacerle commit)
- - -
git log --stat (ver todos los cambios de que han hecho en los archivos)
- - -
git checkout |master || ...a0f56ade7 | archivo.txt 
- - -
git reset o git rm
- - -
git clone url (clonar una url que sea donde vamos a subir los documentos)
- - -
git push (llevar de nuestr equipo local a la nube o internet)
- - -
git fetch (traer de nuestra nube o internet a nuestro equipo local)
	- - -
	git merge (une la informacion que tenemos en la nube con nuestro equipo local y los fusiona)
	o
	git pull (unión entre git fetch y git merge)
- - -
git branch xxxxxxxxx (rama o branch para determinar los distintos nombre)
- - -
git checkout xxxxxxx (cambio de rama a rama)
- - -
git merge (rama que desea copiar) "mensaje a mostrar"
- - -
git checkout master
(master) git merge cabecera "mensaje a mostrar"
- - -
* * *
adicionar un repositorio remoto 
- - -
* * *
git remote add origin https://github.com/oscardo/cursogithub.git
- - -
git remote 
	origin
- - -
git remote -v
origin  https://github.com/oscardo/cursogithub.git (fetch --> descargar los archivos)
origin  https://github.com/oscardo/cursogithub.git (push ---> cargar los archivos)
- - -
git push origin master
- - -
$ git config --global user.email "oscardo@gmail.com"
- - -
$ ssh-keygen -t rsa -b 4096 -c "oscardo@gmail.com"
- - -
$ git log --all --graph --decorate --oneline
alias arbolito="git log --all --graph --decorate --oneline"
- - -
$ git tag -a v0.1 -m "resultado de desarrollo" 725e1ef
gitk
- - -
git push origin cabecera
- - -
- - -
- - -
 creamos otra rama 
 git branch fix-type
 hacemos los cambios que necesitamos realizar
 git push origin fix-type --y subimos los cambios a origin (web) con nuestro cambio con nuestra rama local
 - - -
 - - -
 - - -
comandos útiles para git
- - -
- - -
- - -
1. git clone
 git clone <https://link-con-nombre-del-repositorio>
- - -
2. git branch
 creando una nueva rama:
  git branch <nombre-de-la-rama>
 este comando creará una rama en local. para enviar (push) la nueva rama al repositorio remoto, necesitarás usar el siguiente comando
  git push <nombre-remoto> <nombre-rama>
 visualización de ramas:
  git branch
  git branch --list
 borrar una rama:
  git branch -d <nombre-de-la-rama>
- - -
3. git checkout
 git checkout <nombre-de-la-rama>
hay también un comando de acceso directo que te permite crear y cambiarte a esa rama al mismo tiempo:
 git checkout -b <nombre-de-tu-rama> 
este comando crea una nueva rama en local (-b viene de rama (branch)) y te cambia a la rama que acabas de crear.
- - -
4. git status
el comando de git status nos da toda la información necesaria sobre la rama actual.
 git status	
- - -
5. git add
 git add <archivo>
 git add -a
- - -
6. git commit
 git commit -m "mensaje de confirmación"
- - -
7. git push
después de haber confirmado tus cambios, el siguiente paso que quieres dar es enviar tus cambios al servidor remoto. git push envía tus commits al repositorio remoto.
 git push <nombre-remoto> <nombre-de-tu-rama>
de todas formas, si tu rama ha sido creada recientemente, puede que tengas que cargar y subir tu rama con el siguiente comando:
 git push --set-upstream <nombre-remoto> <nombre-de-tu-rama>
or 
 git push -u origin <nombre-de-tu-rama>
importante: git push solamente carga los cambios que han sido confirmados.
- - -
8. git pull
el comando git pull se utiliza para recibir actualizaciones del repositorio remoto. este comando es una combinación del git fetch y del git merge lo cual significa que cundo usemos el git pull recogeremos actualizaciones del repositorio remoto (git fetch) e inmediatamente aplicamos estos últimos cambios en local (git merge).
 git pull <nombre-remoto>
- - -
9. git revert
 git revert 3321844
después de esto, verás una pantalla como la de abajo -tan solo presiona shift + q para salir:
- - -
10. git merge
 primero, debes cambiarte a la rama dev:
	git checkout dev
antes de fusionar, debes actualizar tu rama dev local:
    git fetch
por último, puedes fusionar tu rama de características en la rama dev:
	git merge <nombre-de-la-rama>
pista: asegúrate de que tu rama dev tiene la última versión antes de fusionar otras ramas, si no, te enfrentarás a conflictos u otros problemas no deseados.
