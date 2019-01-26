# Terminal
## Coventions
- $ : utilisateur avec droits normaux
- # : droits root
- ordre : taille, permissions, date
- droits : groupe, utilisateur, timestamp, nom
- convention : COMMAND + FICHIER + 	PARAMÈTRE(S)
									* -a : un seul tiret
									* -a -b : plusieurs paramètres l'un après les autres
									* -ab : combiner plusieurs paramètres
									* --gelp : paramètres de plusieurs lettres demande deux tirets (-)
- | = pipe pour combiner des commandes
- arborescence : /
	* ~/ : home directory
- d : répértoire
- "-" : fichier
	* puis : droits + utilisateur+groupe+taille+timestamp+date de création
- CTRL + D : pour sortir

## Commandes
- 	man : manuel
- 		+ commande : exemple : man ls
- 	man man
- "q" pour sortir du manuel
- exit
- pwd : répertoire courant
- 	ls : liste des fichiers du répertoire courant (pas les fichiers cachés)
	* ls -l : avec détails
	* ls -a : fichiers cachés
- vous pouvez combiner : ls -la
- cd : se déplacer
		utiliser seul va dans le home directory (~)
- cd .. : revenir en arrière
- cd ../.. : revenir deux dossiers en arrière
- mkdir : créer un répertoire
- rm : effacer
- 	rm -Rf : récursif qui demande pas de confirmations et les sous-répertoires
	rm -Rf *
- touch : créer un fichier
	touch -h -t
- 	cat : regarder à l'intérieur d'un fichier (/!\ binaire)
		* cat FILE
		* cat -e : (non affichable)($=retour à la ligne)
		* cat FILE | grep "x" | head -n 1
		* cat file file 2> erreurs.txt : mettre toutes les erreurs dans ce fichier
		* cat file file file azert > /dev/null : effacer
- echo "x" 	
			* > file : crée (s'il n'existe pas ou remplace s'il existe)
			* >> file : crée ou rajoute à la fin du fichier
			* 2> file : erreurs dans un fichier à part
			* 2>&1
			* 2>>&1

- cp : copier
	* cp SOURCE DESTINATION
- mv : déplacer
- tar -cf file.tar file || tar -cf file.tar *
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
- cat FILE | sort | cut -d, -f 1 | cat -e
- sed "chemin" : modif
- tr "é" "e" : remplacer
- wc : compter. ligne mots caractère
	* wc *
	* cat FILE | grep Thomas | wc -l
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
	echo "1+2"|bc
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



## Droits
- chmod : droits
	* r : read 				- 4
	* w : write 				- 2
	* x : exécuter			- 1
	* 0 : pas de permissions 	- 0
- 	(123) 		(123) 			(123)
	vous		même groupe		reste
- chmod 	000 : aucun droits pour personne
			700 : moi et le reste rien
			644 : juste le lire pour le reste
			-> texte, pas besoin d'exécuter, ce n'est pas du binaire






# EDITORS
## EMACS
- quitter : crtl+x, ctrl+c
- save : ctrl+x, ctrl+s
- back : ctrl+z -> fg
- ligne : ctrl+E | A
- recherche : ctrl+S
- ouvrri un fichier : ctrl+x, ctrl+f
- split : ctrl+X 2 ou ctrl+X 3
	- s'y déplcaer : ctrl+X O
	- fermer le XX?? : ctrl+X 0





## VIM
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