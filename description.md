# Description du dossier
Voici une analyse de livre _Les mystères de Paris. Tome 1_ d'Eugène Sue a éte effectue dans le cadre du cursus "Histoire de Humanités". L'idée est de retravailler le texte pour ensuite l'analyse avec des outils différents et voir le résultat statistique en visualisations. Tout d'abord, je vous présente toutes les étapes techniques et préparatives avant de commencer l'analyse. Ensuite, je ferai l'observation (de la proccesus d'analyse des données) et leur visualisation en utilisant des différents moyens. Enfin, on finira par une conclusion et la réflexion autour d'une question qui a ete pose dans ce devoir. 

## Première étape. TXT
On commence par la récupération des donnees en version textuelle de l'ouvrage. Il est possible de le trouver sur [Wikisource](https://fr.wikisource.org/wiki/Les_Mystères_de_Paris). J'ai pris la première et la deuxième partie car c'est l'ensemble du tome 1.

Puis, j'ai nettoyé le texte en supprimant les notes et en ajoutant des varables que m'a permis d'encoder le texte et importer dans Iramuteq. Le principe d'encodage est suivante :

> Variable : **** *chapitre1_partie1 <br>
> _où la première partie du nom est corresponde au chapitre et le deuxième a la partie du tome_

Bilan : 43 variables.

Lien vers le fichier [(.txt)](https://github.com/soniyabbas/ABBAS_Soniya_LesMysteresdeParis/blob/master/Eugene_Sue_%20Les_Myste%CC%80res_de_Paris.txt)

## Deuxième étape. EPUB
J'ai retrouvé la version de ce livre en format .epub sur Wikisource également, pourtant le texte est divisé en partie. Car moi, j'ai pris "Tome 1" qui compose deux parties, j'ai trouvé un autre site [Gutenberg.org](http://www.gutenberg.org/ebooks/18921) qui propose la possibilité de télécharger le livre par tome avec ou sans images. 

Lien vers le fichier [(.epub)](https://github.com/soniyabbas/ABBAS_Soniya_les_mysteres_de_paris/blob/master/Les_Mysteres_de_Paris_tome_1.epub)

## Troisième étape. Visualisation de données. 

### Statistiques
Après le chargement du text dans Iramuteq on peux obtenir la statistique général du texte en .CSV et le résume sous creteries suivants :

> Nombre de textes : 43 /*(43 variables = chapitres) <br>
> Nombre d'occurrences : 121231 <br>
> Nombre de formes : 6747 <br>
> Nombre d'appax : 2589 (2.14%des occurrences - 38.37% des formes) <br>
> Moyenne d'occurrence par texte : 2819.33 <br>

![Resume](https://github.com/soniyabbas/ABBAS_Soniya_LesMysteresdeParis/blob/master/visualisations/resume.png)

On peut voir sur le graphique la dependence la frequence des mots et la quantité des occurrences. ..._expliquer_

En même temps le logiciel a généré des tableaux .CSV :

- [total.csv](https://github.com/soniyabbas/ABBAS_Soniya_LesMysteresdeParis/blob/master/fichiers%20CSV/total.csv) - la fréquence décroissante des mots utilisés dans le corpus au total et leurs types 
- [formes_actives.csv](https://github.com/soniyabbas/ABBAS_Soniya_LesMysteresdeParis/blob/master/fichiers%20CSV/formes_actives.csv) - les formes les plus actives (les agents pareils : la fréquence et les types)
- [formes_supplémentaires.csv](https://github.com/soniyabbas/ABBAS_Soniya_LesMysteresdeParis/blob/master/fichiers%20CSV/formes_supple%CC%81mentaires.csv) - les mots supplémentaires - secondaires 
- [hapax.csv](https://github.com/soniyabbas/ABBAS_Soniya_LesMysteresdeParis/blob/master/fichiers%20CSV/hapax.csv) - le nombre des mots qui ont été utilisé une fois dans le corpus
 
```xml 
À noter!
```

De la même façon on peut observer qu'une seule chapitre (ou la groupe des chapitres) et récuperer tous les données sur eux. En exemple j'ai réalisé l'analyse statistique du première chapitre (*chapitre1_partie1) : 

> Nombre de textes : 1 <br>
> Nombre d'occurrences : 2962 <br>
> Nombre de formes : 874 <br>
> Nombre d'hapax : 563 (19.01%des occurrences - 64.42% des formes) <br>
> Moyenne d'occurrences par texte : 2962.00 <br>

![Resume_chapitre1](https://github.com/soniyabbas/ABBAS_Soniya_LesMysteresdeParis/blob/master/visualisations/resume_chapitre1.png)

Les tableaux .CSV : 

- [total_chapitre1.csv](https://github.com/soniyabbas/ABBAS_Soniya_LesMysteresdeParis/blob/master/fichiers%20CSV/total_chapitre1.csv) 
- [formes_actives_chapitre1.csv](https://github.com/soniyabbas/ABBAS_Soniya_LesMysteresdeParis/blob/master/fichiers%20CSV/formes_actives_chapitre1.csv)
- [formes_supplémentaires_chapitre1.csv](https://github.com/soniyabbas/ABBAS_Soniya_LesMysteresdeParis/blob/master/fichiers%20CSV/formes_supple%CC%81mentaires_chapitre1.csv)
- [hapax_chapitre1.csv](https://github.com/soniyabbas/ABBAS_Soniya_LesMysteresdeParis/blob/master/fichiers%20CSV/hapax_chapitre1.csv)

### Analyse Factorielle des Correspondances (AFC)
Ce type d'analyse nous proposer de voir la classification hiérarchique descendantes sur une variable ou l'ensemble de variables. Elle organise les données en deux dimessions pour montrer la difference entre les variables ce que nous permet aussi de voir les liasons entre la frequance et le type de mot. 

![analyse_factorielle_des_correspondances](https://github.com/soniyabbas/ABBAS_Soniya_LesMysteresdeParis/blob/master/visualisations/analyse_factorielle_des_correspondances.png)

Ce graphique est réalisé par défaut : la frequance de 10 et deux types de varibles (active et supplementaire).

![analyse_factorielle_des_correspondances_chi2](https://github.com/soniyabbas/ABBAS_Soniya_LesMysteresdeParis/blob/master/visualisations/analyse_factorielle_des_correspondances_chi2.png)

On peut egalement regarder les variables active en changeant la taille de texte proportionnelle au chi2 ce qui finalement exprime par les variables actives.

Car ces deux graphiques sont peu lisible, j'ai fait un autre avec une frequence de 60 en utilisant seulement les formes actives. Cela nous permet d'étudier le fait qu'il y a des correspondances entre les chapitres.

![analyse_factorielle_des_correspondances_active1](https://github.com/soniyabbas/ABBAS_Soniya_LesMysteresdeParis/blob/master/visualisations/analyse_factorielle_des_correspondances_active1.png)

Si on modifie le graphique en appliquant les couleurs, on voit les mots qui sont plus utilisés en fonction deux dimenssions (la taille de texte proportionelle a la masse). 

![analyse_factorelle_des_correspondances_active](https://github.com/soniyabbas/ABBAS_Soniya_LesMysteresdeParis/blob/master/visualisations/analyse_factorelle_des_correspondances_active.png)

La derniere image est la visualisation des modalités suivantes : *chapitre1_partie1,*chapitre1_partie2, *chapitre22_partie2, *chapitre21_partie1 et *chapitre21_partie2. L'idée est de voir les correspondances entre ces chapitres et regarder les dimenssions. 

![analyse_factorielle_des_correspondances_modalités](https://github.com/soniyabbas/ABBAS_Soniya_LesMysteresdeParis/blob/master/visualisations/analyse_factorielle_des_correspondances_modalite%CC%81s-1.png)

![analyse_factorielle_des_correspondances_modalités_video](https://github.com/soniyabbas/ABBAS_Soniya_LesMysteresdeParis/blob/master/visualisations/analyse_factorielle_des_correspondances_modalite%CC%81s_video.gif)

J'ai appliqué dans ce cas la frequance de 10 en utilisant seulement les formes actives. Comme le résultat on a la ... 

### Nuage de mot
Cet analyse est assez simple et represente juste une illustration varible à partir des données qu'on utilise. Le sens est de montrer l'ensemble des mots et en fonction de taille sa frequence. 

![nuage-1](https://github.com/soniyabbas/ABBAS_Soniya_LesMysteresdeParis/blob/master/visualisations/nuage_1.png)
> Que la variable active parmis tous les variables.

![nuage-comp](https://github.com/soniyabbas/ABBAS_Soniya_LesMysteresdeParis/blob/master/visualisations/nuage_comp.png)
> ...
