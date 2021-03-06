# Terminal

### Conventions

- $ : utilisateur avec droits normaux
- \# : droits root
- ordre : taille, permissions, date
- droits : groupe, utilisateur, timestamp, nom
- convention : COMMAND + FICHIER + 	PARAMÈTRE(S)
	* -a : un seul tiret
	* -a -b : plusieurs paramètres l'un après les autres
    * -ab : combiner plusieurs paramètres
	* --gelp : paramètres de plusieurs lettres demande deux tirets (-)
- \| = pipe pour combiner des commandes
- arborescence : /
	* ~/ : home directory
- d : répértoire
- "-" : fichier
	* puis : droits + utilisateur+groupe+taille+timestamp+date de création
- CTRL + D : pour sortir

## Commandes

- 	man : manuel
	- \+ commande : exemple : man ls
- 	man man
- "q" pour sortir du manuel
- exit
- pwd : répertoire courant
- ls : liste des fichiers du répertoire courant (pas les fichiers cachés)
	* ls -l : avec détails
	* ls -a : fichiers cachés
- vous pouvez combiner : ls -la
- cd : se déplacer
	+ utiliser seul va dans le home directory (~)
- cd .. : revenir en arrière
- cd ../.. : revenir deux dossiers en arrière
- mkdir : créer un répertoire
- rm : effacer
- 	rm -Rf : récursif qui demande pas de confirmations et les sous-répertoires
	+ rm -Rf *
	+ rmdir : remove empty directories
- touch : créer un fichier
	+ touch -h -t
- 	cat : regarder à l'intérieur d'un fichier (/!\ binaire)
	* cat FILE
	* zcat : regarder une archive compressée
	* cat -e : (non affichable)($=retour à la ligne)
	* cat FILE | grep "x" | head -n 1
	* cat file file 2> erreurs.txt : mettre toutes les erreurs dans ce fichier
	* cat file file file azert > /dev/null : effacer
- cp : copier
	* cp SOURCE DESTINATION
- mv : déplacer
- tar -cvf nom_archive.tar nom_dossier/ : créer une archive avec tous les fichiers de mon_dossier
	* -c : signifie créer une archive tar
	* -v : signifie afficher le détail des opérations
	* -f : signifie assembler l'archive dans un fichier
- `tar -cf file.tar file || tar -cf file.tar *`
- tar -tf : voir le contenu de l'archive
	* -rvf : ajouter un fichier
	* -xvf : extraire les fichiers de l'archive
- gzip : compresser une archive
- gunzip : décompresser une archive
- tar -zcvf tutoriels.tar.gz tutoriels/
- tar -zxvf tutoriels.tar.gz : décompresser et désarchiver
- tar -ztf : regarder dans une archive gzippée
- ln : lien
- echo
- more
- less
- head
- tail -n (chiffre)
- grep "x" file
	* -v : dégager
	* -i ; variable lettre
- sort
- cut : couper chaque ligne
- `cat FILE | sort | cut -d, -f 1 | cat -e`
- sed "chemin" : modif
- tr "é" "e" : remplacer
- wc : compter. ligne mots caractère
	* wc *
	* `cat FILE | grep Thomas | wc -l`
- file FILE
	- notes.txt: UTF-8 Unicode text
		- notes : à l'état
		- UTF-8 : chaine de charactères
		- text : type de fichier
- lshw : info système
	- short
	- html
- ifconfig : informations sur votre réseau
- inxi -F
- bc : calculatrice
	+ echo "1+2"|bc
- find
	- find /usr -name "ls\*" : trouver tous les fichires dans /usr qui commaence par ls
	- où / quoi / que faire avec
	- find -name "logo.png"
	- size +10M

- locate nom
	- nom : base de donnée
	- sudo updatedb : refaire la bdd

- uniq : supprimer les doublons
- env : toutes les variables dans le shell qui seront passés automatiquement dans vos binaires et scripts
	- sert à paramètrer les scripts shell
	- je veux rajouter une variable "LINE=3"
	- echo $LINE : va donner 3
- faire un : alias ll="ls -lArth"
	* Pour le rendre permanent, modifier le fichier et relancer votre terminal :
	* Bash (par défaut sur Ubuntu) : ~/.bashrc
	* ZSH : ~/.zshrc
- rsync -arv dossier/ dossier2/ : synchroniser deux dossier
	- -a : conserve toutes les informations sur les fichiers, comme les droits (chmod), la date de modification, etc. ;
	- -r : sauvegarde aussi tous les sous-dossiers qui se trouvent dans le dossier à sauvegarder ;
	- -v : mode verbeux, affiche des informations détaillées sur la copie en cours.
	- --delete : supprimer fichiers
	- --backup --backup-dir=/home/user/dossier
- take folder : crée et bascule directement dans un dossier

### Flux de redirection

- echo "x"
	* > file : crée (s'il n'existe pas ou remplace s'il existe)
	* >> file : crée ou rajoute à la fin du fichier
	* 2> file : erreurs dans un fichier à part
	* 2>&1 : fussioner les sorties standard et d'erreur
	* 2>>&1 : la même chose mais à la fin du fichierS
- cat < fichier.txt  : flux entrant. Permet d\'afficher le contenu du fichier
  - à la différence de `cat fichier.txt` où la commande cat recoit en entrée le nom du fichier et se charge de l'ouvrir et l'affichier.
    Ici la commande `cat` reçoit le *contenu* de fichier.txt qu'elle contente simplement d'afficher. C'est le shell qui envoie le contenu du fichier à la commande cat.

- << : permet d'envoyer du contenu à une commande
```shell
	$ wc -m << FIN
	> Combien de caractères dans cette phrase ?
	> FIN
	42
```

### Programmes en arrière-plan

* COMMANDE& : lancer en arrière plan dans la même console
* nohup COMMANDE : détacher le processus de la console
* CTRL+Z : mettre un processus en pause
* bg : passer processus en arrière plan
* jobs : quel processus tournent en arrière-plan
* fg : reprendre un processus en arrière-plan
	* fg %2 : reprendre le processus numero 2

### Droits
- chmod : droits
	* r : read 					- 4
	* w : write 				- 2
	* x : exécuter				- 1
	* 0 : pas de permissions 	- 0
- 	(123) 		(123) 			(123)
	vous		même groupe		reste
- chmod
	* 000 : aucun droits pour personne
	* 700 : moi et le reste rien
	* 644 : juste le lire pour le reste
		* -> texte, pas besoin d'exécuter, ce n'est pas du binaire

## Exemples

- `rename -n 's/.+/our $i; sprintf("a%d.jpg", 1+$i++)/e' *`
	- renommer des fichiers à la volée
- `find . -type d -maxdepth 1 -exec git --git-dir={}/.git --work-tree=$PWD/{} pull origin master \;`
	-	git pull tous les sous-dossiers
- `lk='stat -c "%a %n" *'`
- lm="ls -lArth"

## Scripts Bash

- $# : contient le nombre de paramètres
- $0 : contient le nom du script exécuté
- $1 : contient le premier paramètre
- $2 : contient le second paramètre

## EDITORS

### EMACS

- quitter : crtl+x, ctrl+c
- save : ctrl+x, ctrl+s
- back : ctrl+z -> fg
- `ligne : ctrl+E | A`
- recherche : ctrl+S
- ouvrri un fichier : ctrl+x, ctrl+f
- split : ctrl+X 2 ou ctrl+X 3
	- s'y déplcaer : ctrl+X O
	- fermer le XX?? : ctrl+X 0

### VIM

* :q - quitter
* :q! : forcer à quitter
* :i - insertion
* ÉCHAP - retour
* :w - sauvegarder
* $ - fin de la ligne
* ^ ou 0 - début de la ligne
* :e - nouveau fichier
* :vs - couper buffer verticalement en deux
* CTRL+W : passer d'un buffer à l'autre
* :sp - couper à l'horizontal
	- Ctrl + w puis Ctrl + w : navigue de viewport en viewport. Répétez l'opération plusieurs fois pour accéder au viewport désiré.
	- Ctrl + w puis j : déplace le curseur pour aller au viewport juste en dessous.
	- Ctrl + w puis + : agrandit le viewport actuel.
	- Ctrl + w puis - : réduit le viewport actuel.
	- Ctrl + w puis = : égalise à nouveau la taille des viewports.
	- Ctrl + w puis r : échange la position des viewports. Fonctionne aussi avec « R » majuscule pour échanger en sens inverse.
	- Ctrl + w puis q : ferme le viewport actuel.
* h,j,k,l : se déplacer
* x : effacer lettre
* dw : au début d'un mot, l'efface
* d$ : effacer jusqu'à la fin de la ligne
-	d         - est l'opérateur d'effacement
-	mouvement - est le mouvement sur lequel agit l'opérateur (listés ci-dessous)
-	Une courte liste de mouvements :
    * w - jusqu'au début du prochain mot, en EXCLUANT son premier caractère.
    * e - jusqu'à la fin du mot courant, en EXCLUANT son dernier caractère.
    * $ - jusqu'à la fin de la ligne, en INCLUANT son dernier caractère.
-        opérateur   [nombre]   déplacement
* u : annule la commande
* U : remet toute la ligne
* CTRL+R : annule les annulations
* p : remettre une ligne effacé en dessous
* ce : efface le mot et place en mode insertion
* CTRL+G : numéro de ligne
* numéro de ligne + G : sauter à cette ligne
* /mot : recherche
	* n : retrouver le mot
	* N : direction opposée
	* ? : opposée de /
* % : recherche la paranthèse correspondante
* Pour remplacer le premier aa par bb sur une ligne tapez     :s/aa/bb
     * Pour remplacer tous les aa par bb sur une ligne tapez       :s/aa/bb/g
     * Pour remplacer du texte entre deux numéros de ligne tapez   :#,#s/aa/bb/g
     * Pour remplacer toutes les occurrences dans le fichier tapez :%s/aa/bb/g
     * Pour demander une confirmation à chaque fois ajoutez 'c'    :%s/aa/bb/gc
* v : mode visuel. Puis : pour commande
* :r - insérer du contenu
	* :r !ls
* R - remplacement
* Taper  ":set xxx"  active l'option "xxx". Quelques options sont :
     * 'ic'  'ingnorecase' pour ignorer la casse lors des recherches.
     * 'is'  'incsearch'   pour montrer les appariements partiels.
     * 'hls' 'hlsearch'    pour mettre en surbrillance les appariements.
* :débutdecommande - CTRL+D pour suggestions
