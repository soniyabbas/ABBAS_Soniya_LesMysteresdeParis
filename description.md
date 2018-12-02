# Description du dossier
Voici une analyse de livre _Les mystères de Paris. Tome 1_ d'Eugène Sue a éte effectue dans le cadre du cursus "Histoire de Humanités". L'idée est de retravailler le texte pour ensuite l'analyse avec des outils différents et voir le résultat statistique en visualisations. Tout d'abord, je vous présente toutes les étapes techniques et préparatives avant de commencer l'analyse. Ensuite, je ferai l'observation (de la proccesus d'analyse des données) et leur visualisation en utilisant des différents moyens. Enfin, on finira par une conclusion et la réflexion autour d'une question qui a ete pose dans ce devoir. 

## Première étape. TXT
On commence par la récupération des donnees en version textuelle de l'ouvrage. Il est possible de le trouver sur [Wikisource](https://fr.wikisource.org/wiki/Les_Mystères_de_Paris). J'ai pris la première et la deuxième partie car c'est l'ensemble du tome 1.

Puis, j'ai nettoyé le texte en supprimant les notes et en ajoutant des varables que m'a permis d'encoder le texte et importer dans Iramuteq. Le principe d'encodage est suivante :

> Variable : **** *chapitre1_partie1 <br>
> _où la première partie du nom est corresponde au chapitre et le deuxième a la partie du tome_

Bilan : 42 variables.

Lien vers le fichier [(.txt)](https://github.com/soniyabbas/ABBAS_Soniya_les_mysteres_de_paris/blob/master/Eugene_Sue_%20Les_Myste%CC%80res_de_Paris.txt)

## Deuxième étape. EPUB
J'ai retrouvé la version de ce livre en format .epub sur Wikisource également, pourtant le texte est divisé en partie. Car moi, j'ai pris "Tome 1" qui compose deux parties, j'ai trouvé un autre site [Gutenberg.org](http://www.gutenberg.org/ebooks/18921) qui propose la possibilité de télécharger le livre par tome avec ou sans images. 

Lien vers le fichier [(.epub)](https://github.com/soniyabbas/ABBAS_Soniya_les_mysteres_de_paris/blob/master/Les_Mysteres_de_Paris_tome_1.epub)

## Troisième étape. Visualisation de données. 
