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
					- Et	: http://git-scm.com/docs/pretty-formats
				- git log --merges -2  // afficher les deux merges les plus récents
				- git log --no-merge  // ne veut pas consulter les commits issus des merges 
				- git log --pretty=%P -1 // Pour identifier le commit parent d’un commit
			- tag :
				- git checkout hash_du_commit // Pour créer un tag léger, il faut se positionner sur le commit dont on veut créer un alias 
				- git tag nom_du_tag hash // créer un tag sans se positionner sur le commit en utilisant la commande git tag tout en spécifiant le hash du commit 
					- exemple git tag v1.8.6 af31a4
				- git tag nom_du_tag 
					- exemple : git tag v1.8.5 
				- git tag -a nom_du_tag // tag annoté
				- git tag -a nom_du_tag -m "message_du_tag" 
				- git tag --list // lister uniquement les noms des tags
				- git show v1.8.5 // Afficher les détails d’un tag va également afficher les détails du commit auquel le tag est associé
				- git push origin --tags // envoyer les tags un à un vers le dépôt distant
				- git tag -d nom_du_tag // Pour supprimer un tag
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
			- git remot // avoir la liste des dépôts distants liés au dépôt local
			- git remote add origin 
			- git remote -v
			- git pull // mettre à jour la branche courante avec les commits contenus dans le dépôt distant
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
		- Graphique généré à l’aide de gitgraph.js disponible sur GitHub (https://github.com/nicoespeon/gitgraph.js)
	 	- Commande :
	 	 	- git branch // afficher la liste des branches,
	 	 	- git branch <name> // pour créer la branche 
			- git branch -v // afficher la liste des branches avec le hash et le message du dernier commit
			- git checkout <name> // Changer de Branch
			- git merge // Fusion de branch
	- Dépôt
		- git init --bare new_browser  // création d’un dépôt distant Git vierge
		- git clone ssh://nomdudepot // cloner un dépôt
		- git clone http: nomdudepot 
	
	- Vincent Driessen a proposé un système efficace de gestion des branches sur son blog professionnel (http://nvie.com/posts/a-successful-git-branching-model).

1. Les branches éternelles

Les branches master et develop sont les branches qui ne seront jamais supprimées pendant toute la durée de vie du projet. 
Ce sont les seules branches à exister au début du projet et à la fin du projet.

a. La branche de production (master)
	
Cette branche est la branche qui contiendra toutes les versions publiées pour les utilisateurs. 
C’est-à-dire que c’est cette branche qui recevra toutes les nouvelles fonctionnalités et toutes les corrections de bugs. 
Chaque commit de cette branche est représenté par une nouvelle version spécifiée par un tag.
Tous les commits de cette branche sont des commits produits par les merges d’autres branches (à l’exception du commit d’origine).

Voici les branches qui peuvent être créées à partir de master :

- La branche develop (qui ne sera créée qu’une seule fois au début du projet).

- Les branches de correctifs (hotfix).

Voici les branches dont master pourra recevoir les modifications au travers d’un merge :

- Les branches de nouvelles versions (release).

- Les branches de correctifs (hotfix).

b. La branche de développement (develop)
	
La branche de développement correspond à la branche qui recevra toutes les nouvelles fonctionnalités qui ne sont pas encore intégrées à la version principale. Cette branche correspond aux futures versions qui seront publiées et n’est pas encore considérée comme stable. 
Cette branche est créée dès le début du projet à partir de la branche master.

Voici les branches qui peuvent être créées à partir de la branche develop :

- Les branches de fonctionnalités (feature).

- Les branches de versions (release).

Voici les branches à partir desquelles develop pourra recevoir les modifications :

- Les branches de correctifs (hotfix).

- Les branches de versions (release).

- Les branches de fonctionnalités (feature).

2. Les branches éphémères

Les branches éphémères sont des branches qui ont une durée de vie limitée.
Elles sont créées dans un but très précis et, une fois celui-ci accompli, ces branches sont supprimées.

a. Les branches de versions (release)
	
Ces branches sont des branches de versions Beta du projet. Prenons l’exemple d’un logiciel dont la version 2.0 est prévue très prochainement. 
L’entreprise éditrice décide un mois avant la publication de cette version de créer une branche release pour préparer cette sortie. 
Avant de créer cette branche, l’entreprise doit s’assurer que toutes les nouvelles fonctionnalités attendues pour la version 2.0 ont été intégrées dans la branche develop. 
Une fois que cette vérification est effectuée, la branche release-2.0 peut être créée à partir de la branche develop. Cette branche aura deux utilités principales :

Elle va servir à rendre la prochaine version stable. C’est-à-dire que la branche release-2.0 sera testée au maximum et que des correctifs spécifiques aux nouvelles fonctionnalités seront inclus dans cette branche.

Cette branche va permettre aux développeurs de commencer à travailler sur les fonctionnalités de la version 3.0 pendant que la version 2.0 est en phase de test. Aucune fonctionnalité propre à la version 3.0 ne doit se trouver dans la branche release-2.0.

Cette branche ne sert pas à recevoir de nouvelles fonctionnalités. Elle doit être créée à partir de develop qui doit contenir toutes les nouvelles fonctionnalités de la version 2.0.

Cette branche sera mergée dans les branches develop et master. Le commit dans la branche master donnera lieu à un commit sur lequel le tag v2.0 sera appliqué.

Cette branche sera supprimée après avoir été mergée dans master et develop.

b. Les branches de correctifs (hotfix)

Ces branches sont celles qui vont accueillir les correctifs destinés à la production. 
La création d’une branche de correctifs survient lorsqu’un bug est découvert et que le développeur commence à le corriger. 
Le ou les commits de cette branche sont uniquement des commits destinés à la résolution du bug (et la mise à jour des numéros de versions si nécessaire).

Une branche de correctif est créée à partir de la branche master et, une fois le correctif commité, cette branche sera mergée dans master et dans develop et sera ensuite supprimée. 
Pour respecter la norme de Git-Flow, il faut préfixer les noms des branches de correctifs par hotfix-.

c. Les branches de fonctionnalités (feature)

Chacune des branches de fonctionnalité a pour but d’intégrer une nouvelle fonctionnalité à la branche develop.
Ces branches sont locales, c’est-à-dire qu’elles ne sont pas partagées sur le dépôt central. 
La création d’une telle branche a toujours lieu à partir de la branche develop et lorsque la nouvelle fonctionnalité est créée et commitée, cette branche doit être intégrée à develop.

Lorsque la fonctionnalité a été intégrée à develop, la branche de fonctionnalité doit être supprimée.

d. Plusieurs commits dans une branche éphémère ?

Il est tout à fait possible d’avoir plusieurs commits dans une branche éphémère. 
Il faut cependant garder à l’esprit qu’il est important de créer une branche par développement indépendant.

En effet, si on prévoit plusieurs commits dans une branche, il faut que le blocage d’un commit (le temps de faire des corrections suite à une revue de code, par exemple) ne soit pas dérangeant.

Dans une entreprise qui déploie constamment de nouvelles versions et qui n’utilise pas de branche de type release, il est possible d’imaginer deux branches de fonctionnalité :

f-ajout-paiement

- Commit aef523 -- Paiement : Ajout carte bancaire

- Commit 24a56e -- Paiement : Ajout bitcoin

f-ajout-mode-livraison

- Commit bc85d1 -- Livraison : Choix du mode

- Commit 45a56c -- Livraison : Facturation du mode

Dans ces deux exemples de branches, il y en a une qui est mal définie.

La branche f-ajout-paiement contient deux commits indépendants. Rien n’empêcherait de mettre en place un paiement par carte bancaire sans le paiement par Bitcoin et inversement. 
Le problème de cette branche est que si une revue de code bloque un des commits (le paiement en Bitcoin, par exemple), il ne sera pas possible de mettre l’autre sur la branche develop (puis sur master). 
On s’interdit donc de mettre en place le paiement en carte bancaire tant que celui par Bitcoin n’est pas totalement terminé, alors qu’utiliser deux branches distinctes aurait réglé le problème.

La branche f-ajout-mode-livraison est correctement définie. En effet, le choix du mode de livraison sur le formulaire de commande ainsi que la facturation des différents modes sont indissociables. 
On ne va pas facturer un mode dont ne bénéficie pas le client et on ne va pas offrir la livraison au client (sauf choix commercial).
	
---
