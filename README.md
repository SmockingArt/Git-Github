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
			- git init	// initialisation d'un fichier git
			- git status	// voir les dossier save
			- git log	// voir les différents commit
			- git add .	// save dossier
			- git touch	// crée un fichier
			- git mv <ancien_nom> <nouveau_nom> ou déplacer le fichier 
	- les changements
		- Commande :
			- git commit -m "ici le commentaire"
			- git pull 
			- git push origin master 
	- Ignorer les fichiers
		- Commande :
			- .gitignore	// fichier de conf pour ignorer certain fichier
			- git rm --cached nomDuFichier // Enlever le cache de git
	- Récupérer une version d’un fichier
		- Commande :
			- git reset // Enlevé de git add
			- git reset -- hard // Enlevé de git add et supprimé les modifications
	- Branch 
	 	- Commande :
	 	 	- git branch 
	 	 	- git branch <name> // Crée une branch 
			- git checkout <name> // Changer de Branch
			- git merge // Fusion de branch
---
