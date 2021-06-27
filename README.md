# AutoLabelme_ReadME
This is a ReadMe for using AutoLabelme. 


	Ouvrir deux terminaux Anaconda PowerShell Prompt (ml_env)
	1 : Dans l’un d’eux : 
	taper la commande labelme et appuyer sur entrée (ouverture du labelme)
	2 : Dans l’autre : 
	taper la commande : cd  .\Downloads\AutoLabelme\ et appuyer sur entrée 
	taper la commande : python .\AutoLabelme.py et appuyer sur entrée  (ouverture du AutoLabelme)

	3 : Dans le Labelme : 
	Ouvrir un fichier (image au format JPG)
	Créer une vignette « référence » pour chaque ligne avec Ctrl+R (le premier clic peut être fait en haut à gauche ou en bas à droite de chaque vignette et peut être pris à n’importe quel emplacement sur la ligne)
	Pour certaines lignes, il est préférable de créer les labels à main levée : en créer un puis le dupliquer (Ctrl+D) surtout dans le cas où les délimitations des ornements ne sont pas du tout claires (à faire à l’étape 5)
	Enregistrer l’image (Ctrl+S ou Save dans la barre d’outils à gauche qui sera sauvé au format JSON)

	4 : Dans AutoLabelme : 
	Ouvrir le fichier image préalablement sauvé dans Labelme ( File puis Open JSON en haut à gauche de la fenêtre)
	Cliquer sur le bouton ‘Next line >>’ pour débuter la détection
•	Si trop de cases sont affichées : cliquer sur le bouton  ‘ – ‘, s’il y en a trop peu, cliquer sur ‘ + ‘. Il est possible d’entrer des valeurs dans la case Search Space pour avoir moins de lignes détectées (dans le cas de petits ornements).
•	Si des ornements ont une rotation : rentrer un intervalle d’angles de rotation (‘Rotation Range’ : ‘Min’ et ‘Max’) 
•	Les labels détectés s’affichent en rouge, celles miroir (symétrie par rapport à un axe vertical) et celles inversées (symétrie par rapport à un axe horizontal) en bleu et celles miroir et inversés en vert. Si l’utilisateur considère que les labels bleus ne devraient pas l’être il faut alors appuyer sur le bouton ‘Correct Label’.  Toutes les labels seront alors considérés comme n’étant pas symétriques et seront rouges. Il est possible de revenir en arrière et d’avoir des labels et leurs symétriques en appuyant sur le bouton ‘Rematch’

	Cliquer sur le bouton ‘<< Previous line’ pour voir les labels des lignes précédentes (si nécessaire)

	Une fois tous les labels détectés : appuyer sur le bouton ‘Save JSON’ (un fichier appelé par : fichier_matched.JSON) sera alors créé dans le même répertoire que le fichier JSON)

	5 : Retour dans Labelme : 
	Ouvrir le fichier_matched.JSON, le modifier (ajouter des labels si besoin comme indiqué à l’étape 3 ou en supprimer ; ajuster les vignettes) si nécessaire puis sauver le fichier à nouveau 

	6 : Retour dans AutoLabelme :
	Appuyer sur le bouton ‘Save Images’, un dossier templates est créé dans lequel se trouve tous les répertoires des labels détectés .

 
Explications des touches : 
1.	‘ Next line >> ‘ : Détection du prochain label
2.	‘<< Previous line ‘ : Détection du modèle précédent
3.	‘-‘ : Augmente le seuil, sélectionne moins de case
4.	‘+’ : Diminue le seuil, sélectionne plus de cases
5.	‘Save JSON’ : Sauvegarde un fichier JSON qui peut être lu par Labelme pour le modifier.
6.	‘Save Images’ : Sauve les vignettes découpées 
7.	‘min’ : valeur minimum d’angle pour la Rotation
8.	‘max’ : valeur maximum d’angle pour la Rotation
9.	‘Remacth’ : Refait le label de la ligne actuelle
10.	 ‘Search space’ : Par défaut, la valeur est de 2, ce qui signifie que l’algorithme cherchera les vignettes de deux hauteurs plus haut et plus bas que la vignette originale. Il est possible de choisir une valeur entre 1 et 15. Par exemple, si une vignette commence aux coordonnées (200,200), la hauteur et la largeur valent 100 et le ‘Search  space’ vaut 2, l’algorithme recherchera des vignettes sur toute les lignes avec une hauteur comprise entre 0 et 400 ( (:,0) à ( :,400) ). Si l’utilisateur applique une valeur supérieure à 15, uniquement la hauteur sera prise en considération. En choisissant 100 avec l’exemple précédent, les vignettes seront cherchées sur toutes les lignes pour une hauteur comprise entre 100 et 300 ( ( :,100) à ( :,300) ). 
	
