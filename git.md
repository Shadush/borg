- git init
- git help config * 
				* --global
				*	--local
- variable : 	* user.email
				* user.name
- git config --global user.email "@"
- git config --global user.name "name"
- git config --global colir.ui true
- git config --list

- git status
- git add file : (stager)
- git commit
			 * --ammend : corriger commentaire
			 * -m "message" : raccourci pour aller plus vite
			 * -a (-m) : à la volée
- git add "*.txt"
- git add --all
- .gitignore : ```	*.tmp
				file
				dossier/* ```
- git log 
		--stat : résumé
		-n 2
- git log --online : sur une seule ligne
- git log -p "chemin du fichier" : détails des lignes modifiés
- git rm
- ex : git log -p readme.md
- git diff
- git clone
- git push (ne pas oublier la destination lors du 1er push : "origin master" par exemple)
- git pull
- git checkout : annule les changements
- git checkout HEAD filename : annule changements
- git reset HEAD filename : unstage
- git reset commit_sha : reset
- git branch title
- git branch
- git checkout -b branch_name
- git merge branch_name
- git branch -d branch_name
- git clone remote_location clone name
- git remote -v : list of Git's projects remotes
- git fetch
- git push origin branch

- git cherry-pick (pas utilisé)
- git revert (pas utilisé)
- git rebase (pas utilisé)

- git branch	
				* -d name : supprimer
				* -D name : annuler
- git stash : mise à côté et sauvegardé
- git stash apply : recup
- git stash pop : vider stash
- git branch -r : list
- git branch --track branche_local origin/branch_server
	-> connecté
- git checkout -b mabranche
- git revert 1111
- git push origin origin : refs/heads/nouvellebranche : ajouter ou supprimer une branche sur le serveur
- git branch -r -d origin/branch à supprimer
- git tag nomtag idcommit
- git push --tags : car ce n'est pas automatique
- git tag -d NOMTAG : supprimer tag
- git reset HEAD  : dernier commit
- git reset 	
				* ^ : avant dernier commit
				* ^^ : avant avant dernier commit
				* -2 : avant avant dernier commit (notation)
			* --hard HEAD^ : annule les commits et perd tous les changements
- git grep "à chercher"
- git grep -n "x" avec le numéro de ligne

- git mergetool vimdiff
				gvimdiff
- git blame fichier
- git show idcommit

- git init --bare : dépôt avec uniquement .

- git checkout -b ma-branche

- git log -p : détails des lignes modifiées
- git log --stat : résumé
- git commit --amend : corriger commentaire

- git reset 	HEAD : dernier commit
			* HEAD^ : avant-dernier commit ;
			* HEAD^^ : avant-avant-dernier commit ;
			* HEAD~2 : avant-avant-dernier commit (notation équivalente) ;
			* 111 : numéro de commit précis
- git reset --hard HEAD^   /!\ Annule les commits et perd tous les changements

- git checkout : anuler les modifications d'un fichier avant un commit
- git reset HEAD -- fichier_a_supprimer : annuler, supprimer un fichier avant un commit
- git pull : télécharger les nouveautés
- git revert 111

- git remote add origin url_serveur
- git push origin master
- git push -u origin master
## Raccourcis
- gaa
- gcmsg
- gpom="git push origin master"

## Kerberos
- klist
- kdestroy
- kinit username