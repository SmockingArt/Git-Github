# Git-Github
---
Concepts clés: 

Source : Eni - Le Wagon - Video 

Auteur/Projets :  Formation 

Tags : #git #Github

✍  Fais part : @SmockingArt

🧭 Date : 2023-06-02


***

# My Git - GitHub | post-it


- [x] Débuter avec GIT
	- Initialiser un projet
	- Git Bash
		- Commande : 
			- git config --help Ou Git config --h	//En ligne de commande
			- git contig --global user.name "SmockingArt"
			- git contig --global user.email "smockingart_dm@hotmail.com"
			- git contig --global --edit
			- git config --global core.editor vi // vi comme éditeur par défaut
			- git config --global commit.template ~/gitRessources/template.txt // Template pour commentaire 
			- git config --global core.excludesfile ~/.gitignore_global  // Ignore les fichier à commit
			- git config --global alias.co checkout // définir un alias qui va servir de raccourci pour l’appel des commandes.
			- git config --global alias.last 'log -1 HEAD' //
			- git config --global extendedRegexp = true // Activation des expression régulières
				- Alias :
				 	- alias.st : status
					- alias.co : checkout
					- alias.ci : commit
		- Pagination git diff :
		 	- git config --global pager = cat  // meilleur visibilité
		- Initialiser :
			- git init	// initialisation d'un fichier git
			- git status	// voir les dossier save
			- git add .	// save dossier
			- git touch	// crée un fichier
			- git mv <ancien_nom> <nouveau_nom> ou déplacer le fichier 
			- git rm 	// Suprimer un fichier
		- git log :
			- git log	// voir les différents commit
				- git log -n // nombres de commit à afficher 
				- git log -n --stat // donne plus d'information modificaton
				- git log --before="2015-02-09" // gestion par date
				- git log --after="2015-02-09" 
				- git log --after="2015-02-09" --before="2015-02-13" 
				- git log --since=1.weeks 
				 	- days : jours.
					- months : mois.
					- years : années.
				- git log -3 --author "Tim Graham"  // gestion commit par Auteur
				- git log -3 --author "Edward Henderson\|Tim Graham" 
				- git log --graph --oneline -8  // commit en graph ligne de commande 
				- git log --graph --pretty=format:  // Graph avancer 
					- Voir	: http://git-scm.com/docs/pretty-formats
					- Et	: http://git-scm.com/docs/pretty-formats)
				- git log --merges -2  // afficher les deux merges les plus récents
				- git log --no-merge  // ne veut pas consulter les commits issus des merges 
				- git log --pretty=%P -1 // Pour identifier le commit parent d’un commit
		- git diff : 
			- git diff // Pour afficher les différences entre le répertoire de travail et l’index
			- git diff HEAD // comparer ces deux zones sans se soucier de l’index
			- git diff commit1..commit2 
			- git diff F8cc464..HEAD // les modifications introduites par le dernier commit
			- git diff --color-words=. // affiche les mots modifié
			- git diff --word-diff // commande équivalente 
			- git diff --color-moved // pour afficher différemment les blocs de code déplacés des blocs ajoutés et supprimés.
	- les changements
		- Commande :
			- git commit -m "ici le commentaire"
			- git remote add origin 
			- git remote -v
			- git pull 
			- git push origin master 
			- git commit --amend // modifier le contenu de son dernier commit
			- git commit --amend --no-edit // modifier le contenu de son commit sans modifier le message de commit 
			- git shortlog // afficher un résumé des commits
				- voir	: https://git-scm.com/docs/git-shortlog
	- Ignorer les fichiers
		- Commande :
			- .gitignore	// fichier de conf pour ignorer certain fichier
			- git rm --cached nomDuFichier // Arrêter de suivre un fichier 
	- Récupérer une version d’un fichier
		- Commande :
			- git reset // enlevé de git add
			- git reset head // remettre l’index dans le même état que la version la plus récente du dépôt
			- git reset -- hard HEAD // enlevé de git add et supprimé les modifications
			- git reset hash_du_commit // revenir à un état antérieur en utilisant le hash du commit
			- git restore fichier // permet également de restaurer l’état de fichiers du répertoire de travail à partir de l’index.
			- git restore --staged fichier // restaurer l’état du fichier à partir de HEAD
	- Branch 
	 	- Commande :
	 	 	- git branch 
	 	 	- git branch <name> // Crée une branch 
			- git checkout <name> // Changer de Branch
			- git merge // Fusion de branch
---
