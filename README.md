GIT PRIMEROS PASOS DE ESTO!!!

- - -
[WEB SITE DE MARKDOWN] https://markdown.es/sintaxis-markdown/
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
- - -
# **git pull** 

es un comando de Git utilizado para actualizar la versión local de un repositorio desde otro remoto.

Es uno de los cuatro comandos que solicita interacción de red por Git. Por default, git pull hace dos cosas.  

Actualiza la rama de trabajo actual (la rama a la que se ha cambiado actualmente)
Actualiza las referencias de rama remota para todas las demás ramas.
git pull recupera (git fetch) las nuevas confirmaciones y las fusiona (git merge) en tu rama local.

La síntaxis de este comando es el siguiente:

# **Formato General**
git pull OPCIONES REPOSITORIO REFSPEC

**Pull de una rama específica**
*git pull NOMBRE-REMOTo NOMBRE-RAMA*
En donde:

**OPCIONES** son las opciones de comandos, como --quiet o --verbose. Puedes leer más sobre las diferentes opciones en la Documentación de Git.
**REPOSITORIO** es la URL de tu repositorio. Por ejemplo: https://github.com/freeCodeCamp/freeCodeCamp.git
**REFSPEC** especifica cuáles referencias recuperar y cuáles referencias locales actualizar.
**NOMBRE-REMOTO** es el nombre de tu repositorio remoto. Por ejemplo: origin.
NOMBRE-RAMA es el nombre de tu rama. Por ejemplo: develop.
Nota

Si tienes cambios no confirmados, la parte de fusión del comando **git pull** *fallará* y tu rama local quedará intacta.

Por lo tanto, siempre deberías confirmar tus cambios en una rama antes de actualizar nuevas confirmaciones de un repositorio remoto.

Tabla de Contenidos

Usando git pull
Control de Versiones Distribuido
**git fetch + git merge**
**git pull** en IDEs
Usando git pull
*Usa git pull para actualizar un repositorio local del repositorio remoto correspondiente. Por ejemplo: Mientras trabajas localmente en main, ejecuta git pull para actualizar la copia local de main y actualizar las otras ramas remota de seguimiento remoto. (Más información sobre referencias de rama remota en la siguiente sección).*

Sin embargo, hay algunas cosas que hay que tener en cuenta para que ese ejemplo sea cierto:

El repositorio local tiene un repositorio remoto vinculado.

Confirma esto ejecutando *git remote -v*
Si existen múltiples remotos, *git pull* podría no ser suficiente información. 
Es posible que debas ingresar **git pull origin** o **git pull upstream**.
La rama a la que te has movido tiene una rama de seguimiento remoto correspondiente.

Revisa esto ejecutando **git status**. Si no hay una rama de seguimiento remota, Git no sabe de dónde extraer la información.
Control de versiones distribuido

Interacciones de red en Git
Existen solo cuatro comandos que solicitan interacción de red en Git. Un repositorio local no tiene conocimiento de los cambios hechos en un repositorio remoto hasta que hay una solicitud de información. Y, un repositorio remoto no tiene conocimiento de los cambios locales hasta que las confirmaciones son enviadas.

Los cuatro comandos de red son:

**git clone**
**git fetch**
**git pull**
**git push**
Ramas en DVCS
Cuando trabajas con Git, puede parecer que hay demasiadas copias del mismo código flotando por todas partes. Hay diferentes versiones del mismo archivo en cada rama. Y, diferentes copias de la misma rama en la computadora de cada desarrollador y en la remota. Para mantener el seguimiento, Git usa algo llamado referencias de rama remota.

Si ejecutas **git branch --all** dentro de un repositorio de Git, las referencias de rama remota aparecen en rojo. Estas son copias de solo lectura del código y como aparece en el control remoto. (¿Cuándo fue la última interacción de red que habría traído información localmente? Recuerda cuando se actualizó la información por última vez. La información en la referencia de rama remota refleja la información de esa interacción).

Con las referencias de rama remota, puedes trabajar en Git en varias ramas sin interacción de red. Cada vez que ejecutes los comandos **git pull** o **git fetch**, actualizas las referencias de rama remota.

**git fetch más git merge**
**git pull** es un comando combinado, que equivale a **git fetch + git merge**.

## **git fetch**

Por sí mismo, **git fetch** actualiza todas las referencias de rama remota en tu repositorio local. En realidad, no se reflejan cambios en ninguna de las ramas de trabajo locales.

## **git merge**

Sin ningún argumento, **git merge** fusionará la referencia de rama remota correspondiente a la rama de trabajo local.

## **git pull**

**git fetch** actualiza las referencias de ramas remotas. **git merge** actualiza la rama actual con la referencia de rama remota correspondiente. Utilizando git pull, obtienes ambas partes de estas actualizaciones. Pero, esto significa que si te mueves a la rama feature y ejecutas git pull, cuando te muevas a master, cualquier nueva actualización no estará incluida. Cuando te muevas a otra rama que pudiera tener nuevos cambios, siempre es buena idea ejecutar  git pull.
[ver referencia] (https://www.freecodecamp.org/espanol/news/git-pull-explicado/)

