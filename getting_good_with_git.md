#Getting Good With Git
![image](http://rockable.heroku.s3.amazonaws.com/sites/4f4d642a3c70e60001000008/contents/content_instance/4f6acce826a2340001000153/files/L_GettingGoodwithGit.png)

[**URL del libro**](http://rockablepress.com/books/getting-good-with-git)

**Autor:** Andrew Burgess

##Contenido
* `git init`
* `git status`
* `git clone`
* `git add`
		
		git add -i // Modo interactivo.
		git add -p // Para ir marcando qué cambios entran y cuales no en el commit.
		
* `git commit`

		git commit ---amend // Amend ~ enmendar / corregir.

* `git log`

		git log --all (para todas las ramas)
		git log --all --graph (pinta las líneas como un árbol) --oneline (versión comprimida del log)
		
* `git branch` // Listado de todas las ramas.

		git branch -a // Lista todas las ramas, tanto locales como remotas.
		git branch <nombre> // Crea una rama, y coloca un * delante de la rama activa.

* `git checkout <nueva_rama>` // Cambia de rama.

		git checkout -b <branch> // Crea la rama y se cambia a ella.
		git checkout puede utilizarse como un reset para un determinado archivo: 
    		git checkout -- file.txt (con -- se indica que es la versión que hay en el staging area).
			git checkout HEAD file.txt // HEAD indica el commit, se puede utilizar cualquiera de los que aparecen a continuación.
			
* `git diff <file>`

		git diff --cached <file> // Compara la versión del stagin area con el último commit.
		git diff HEAD^2 // Compara con el commit indicado.
		git diff branch1..branch2 // Para comparar la branch 1 y la 2.
		git diff branch1…branch2 // Compara el último commit de branch2 con el ancestro más cercano de branch1.
	
* `git stash` // Realiza un commit temporal.
		
		git stash list // Lista los stash que hay creados.
		git stash save <mensaje> // Para poner un mensaje al guardar el stash.
		git stash apply  // Para volver a poner el contenido modificado.
		
		para "aplicar un determinado stash" (puede haber varios):
		git stash apply stash@{1} // El hash del commit se puede sacar del listado de stashs.
		
* `git merge <rama_a_mergear>` // Hace merge de la rama sobre la rama activa.
* `git reset`
		
		git reset --hard HEAD // Vuelve al estado del último commit, eliminando todos los cambios que hubiésemos hecho desde entonces.
		git reset --soft <hash_commit> // Vuelve al commit indicado (convirtiendose en el HEAD del repositorio) y deja nuestros cambios.

* `git show <etiqueta>` // para ver información sobre una etiqueta.
* `git describe` // muestra cuantos commits distan de la última etiqueta ANOTADA.
	
	Devuelve algo de la forma: *<tag>-<nº de commits que distan>-g<hash>*
	
* `git pull origin master`
 
		// Es lo mismo que si ejecutamos dos comandos:
		* git fetch origin master
		* git merge origin/master
		
* `git push origin master`
* `git rebase` // Mete los commits de una rama en la rama actual, para evitar el merge.

###Tags
Hay dos tipos:

* lightweight // Son un puntero .gittag
* annotated // Crea un commit nuevo.

`git tag -a <etiqueta> -m <mensaje>` (el mensaje es opcional)


###Archivo .gitignore:
		*.log
		!errors.log
		
		se ignora todo menos el fichero errors.




###Referenciar commits
* SHA-1 hash (el hash que aparece en el log, por ejemplo). Suele bastar con los 7 primeros caracteres.
* La rama / tag / nombre remote.
* Especificación de fecha:

	`feature@{4 days ago}` // feature es la rama y 4 days ago la especificación de la fecha.
* Especificación ordinal:
	
	`feature@{3}` // Obtiene el antepenúltimo commit.
* `HEAD` // Apunta al último commit de la rama actual.
		
		HEAD^ // Padre del último commit.HEAD^2 // El commit en otra rama.
		HEAD~ // Padre del padre del último commit.
		HEAD~2 // Great-grand parent commit.