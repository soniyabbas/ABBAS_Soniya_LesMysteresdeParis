# Description du dossier
Voici une analyse de livre _Les mystères de Paris. Tome 1_ d'Eugène Sue a éte effectue dans le cadre du cursus "Histoire des Humanités". L'idée est de retravailler le texte pour ensuite l'analyse avec des outils différents et voir le résultat statistique en visualisations. Tout d'abord, je vous présente toutes les étapes techniques et préparatives avant de commencer l'analyse. Ensuite, je ferai l'observation (de le processus d'analyse des données) et leur visualisation en utilisant des différents moyens. Enfin, on finira par une conclusion et la réflexion autour d'une question qui a ete pose dans le cadre de TD. 

## Première étape. TXT
On commence par la récupération des données en version textuelle de l'ouvrage. Il est possible de le trouver sur [Wikisource](https://fr.wikisource.org/wiki/Les_Mystères_de_Paris). J'ai pris la première et la deuxième partie car c'est l'ensemble du tome 1.

Puis, j'ai nettoyé le texte en supprimant les notes et en ajoutant des variables que m'a permis d'encoder le texte et importer dans Iramuteq. Le principe d'encodage est suivant :

> Variable : **** *chapitre1_partie1 <br>
> _où la première partie du nom est corresponde au chapitre et le deuxième a la partie du tome_

Bilan : 43 variables.

Lien vers le fichier [(.txt)](https://github.com/soniyabbas/ABBAS_Soniya_LesMysteresdeParis/blob/master/Eugene_Sue_%20Les_Myste%CC%80res_de_Paris.txt)

## Deuxième étape. EPUB
J'ai retrouvé la version de ce livre en format .epub sur Wikisource également, pourtant le texte est divisé en partie. Car moi, j'ai pris "Tome 1" qui compose deux parties, j'ai trouvé un autre site [Gutenberg.org](http://www.gutenberg.org/ebooks/18921) qui propose la possibilité de télécharger le livre par tome avec ou sans images. 

Lien vers le fichier [(.epub)](https://github.com/soniyabbas/ABBAS_Soniya_les_mysteres_de_paris/blob/master/Les_Mysteres_de_Paris_tome_1.epub)

## Troisième étape. Visualisation de données. 

### Statistiques
Après le chargement du texte dans Iramuteq on peut obtenir la statistique générale du texte en .CSV et le résume sous critères suivants :

> Nombre de textes : 43 /*(43 variables = chapitres) <br>
> Nombre d'occurrences : 121231 <br>
> Nombre de formes : 6747 <br>
> Nombre d'appax : 2589 (2.14%des occurrences - 38.37% des formes) <br>
> Moyenne d'occurrence par texte : 2819.33 <br>

<p align="center">
  <img src="https://github.com/soniyabbas/ABBAS_Soniya_LesMysteresdeParis/blob/master/visualisations/resume.png">
</p>

Sur le graphique on vois la dependence la fréquence des mots et la quantité des occurrences. Rangs les plus élevés ce sont des mots les plus fréquents. 

En même temps le logiciel a généré des tableaux .CSV :

- [total.csv](https://github.com/soniyabbas/ABBAS_Soniya_LesMysteresdeParis/blob/master/fichiers%20CSV/total.csv) - la fréquence décroissante des mots utilisés dans le corpus au total et leurs types 
- [formes_actives.csv](https://github.com/soniyabbas/ABBAS_Soniya_LesMysteresdeParis/blob/master/fichiers%20CSV/formes_actives.csv) - les formes les plus actives sans des articles, propositions, verbes (être et avoir) etc. (les agents pareils : la fréquence et les types)
- [formes_supplémentaires.csv](https://github.com/soniyabbas/ABBAS_Soniya_LesMysteresdeParis/blob/master/fichiers%20CSV/formes_supple%CC%81mentaires.csv) - les mots supplémentaires - secondaires 
- [hapax.csv](https://github.com/soniyabbas/ABBAS_Soniya_LesMysteresdeParis/blob/master/fichiers%20CSV/hapax.csv) - le nombre des mots qui ont été utilisé une fois dans le corpus
 
##### D'une autre façone à analyse

De la même façon on peut observer qu'un seule chapitre (où le groupe des chapitres) et récupérer tous les données sur eux. Par exemple, j'ai réalisé l'analyse statistique du première chapitre (*chapitre1_partie1) : 

> Nombre de textes : 1 <br>
> Nombre d'occurrences : 2962 <br>
> Nombre de formes : 874 <br>
> Nombre d'hapax : 563 (19.01%des occurrences - 64.42% des formes) <br>
> Moyenne d'occurrences par texte : 2962.00 <br>

<p align="center">
  <img src="https://github.com/soniyabbas/ABBAS_Soniya_LesMysteresdeParis/blob/master/visualisations/resume_chapitre1.png">
</p>

Les tableaux .CSV : 

- [total_chapitre1.csv](https://github.com/soniyabbas/ABBAS_Soniya_LesMysteresdeParis/blob/master/fichiers%20CSV/total_chapitre1.csv) 
- [formes_actives_chapitre1.csv](https://github.com/soniyabbas/ABBAS_Soniya_LesMysteresdeParis/blob/master/fichiers%20CSV/formes_actives_chapitre1.csv)
- [formes_supplémentaires_chapitre1.csv](https://github.com/soniyabbas/ABBAS_Soniya_LesMysteresdeParis/blob/master/fichiers%20CSV/formes_supple%CC%81mentaires_chapitre1.csv)
- [hapax_chapitre1.csv](https://github.com/soniyabbas/ABBAS_Soniya_LesMysteresdeParis/blob/master/fichiers%20CSV/hapax_chapitre1.csv)

### Analyse Factorielle des Correspondances (AFC)
Ce type d'analyse nous propose de voir la classification hiérarchique descendante sur une variable ou l'ensemble de variables. Elle organise les données, après transformation statistique, sous forme de graphiques à deux dimensions pour montrer la différence entre les variables ce que nous permet aussi de voir les liaisons entre la fréquence et le type de mot (la relation lexicales plus généralement). 

![analyse_factorielle_des_correspondances](https://github.com/soniyabbas/ABBAS_Soniya_LesMysteresdeParis/blob/master/visualisations/analyse_factorielle_des_correspondances.png)

Ce graphique est réalisé par défaut : la fréquence de 10 et deux types de variables (active et supplémentaire). Il est peu lisible à cause de la grande quantité de données. C'est pourquoi, il est mieux de regarder que les variables actives en changeant la taille de texte proportionnelle au chi2.

![analyse_factorielle_des_correspondances_chi2](https://github.com/soniyabbas/ABBAS_Soniya_LesMysteresdeParis/blob/master/visualisations/analyse_factorielle_des_correspondances_chi2.png)

Pour avoir les données et sa visualisation plus propre, j'ai fait une autre analyse avec une fréquence de 60 en utilisant seulement les formes actives. Cela nous permet d'étudier le fait qu'il y a des correspondances entre les chapitres parmi les mots lesquels utilisent plus de 60 fois. On met en évidence la distance entre les mots.

![analyse_factorielle_des_correspondances_active1](https://github.com/soniyabbas/ABBAS_Soniya_LesMysteresdeParis/blob/master/visualisations/analyse_factorielle_des_correspondances_active1.png)

Si on modifie le graphique en appliquant les couleurs, on voit les mots qui sont plus utilisés en fonction deux facteurs (la taille de texte proportionelle à la masse). 

![analyse_factorelle_des_correspondances_active](https://github.com/soniyabbas/ABBAS_Soniya_LesMysteresdeParis/blob/master/visualisations/analyse_factorelle_des_correspondances_active.png)

La dernière image est la visualisation des modalités suivantes : _*chapitre1_partie1,*chapitre1_partie2, *chapitre22_partie2, *chapitre21_partie1 et *chapitre21_partie2_. L'idée est de voir les correspondances entre ces chapitres et regarder les facteurs. 
Les couleurs ici représentent des chapitres différentes. On peut voir la position des chapitres par rapport aux autres et aussi le placement des chapitres en fonction des facteurs. 

![analyse_factorielle_des_correspondances_modalités](https://github.com/soniyabbas/ABBAS_Soniya_LesMysteresdeParis/blob/master/visualisations/analyse_factorielle_des_correspondances_modalite%CC%81s-1.png)

Cette modélisation 3D montre la possibilité de ce logiciel visualise les données de façon interactive.

<p align="center">
  <img src="https://github.com/soniyabbas/ABBAS_Soniya_LesMysteresdeParis/blob/master/visualisations/analyse_factorielle_des_correspondances_modalite%CC%81s_video.gif">
</p>
>Que les formes actives avec la fréquence de 10.

### Nuage de mot
Cette analyse est assez simple et représente juste une illustration à partir des données qu'on utilise. Le sens est de montrer l'ensemble des mots avec le plus grand nombre d'occurrence qui est déterminé par la taille de la police.

<p align="center">
  <img src="https://github.com/soniyabbas/ABBAS_Soniya_LesMysteresdeParis/blob/master/visualisations/nuage_1.png">
</p>
> Que le variable actif.

Ici on vois _"rodolphe", 'maître", "ecole", "homme"_ etc. Tous ces mots sont autour du sujet principal de ce livre. 

![nuage-comp](https://github.com/soniyabbas/ABBAS_Soniya_LesMysteresdeParis/blob/master/visualisations/nuage_comp.png)
> Sur cette image j'ai réuni 3 graphes différents : nuages de mot des variables "chapitre1_partie1", "chapitre1_partie2" et deux chapitre ensemble. 

Par cette illustration je voulais montrer la quantité des mots les plus représentes et la différence des composants entre deux chapitres.

### Analyse de similitudes (ADS)

L'idée est de présenter la structure des éléments du corpus (comment les mots reliés). Dans cette analyse on peut avoir un résultat plus approfondi car il est base sur les proximités sémantiques et la cooccurrence des mots.  

#### Indice de coocurrences

L'indice de coocurrences calcule combien de fois les mots apparaitre en même temps. J'ai choisi, tout d'abord, les paramètres par défaut : 2760 formes, la présentation - fruchterman reingold (calculation la distance entre les nœuds).

![analyse_de_similitudes_total](https://github.com/soniyabbas/ABBAS_Soniya_LesMysteresdeParis/blob/master/visualisations/analyse_de_similitudes_total.png)

Le graphe est peu lisible. C'est pourquoi ensuite, j'ai retenu seulement 283 formes qui sont égales et supérieres à 30 en divisant les par communautés :

![analyse_de_similitudes_30](https://github.com/soniyabbas/ABBAS_Soniya_LesMysteresdeParis/blob/master/visualisations/analyse_de_similitudes_30_color.png)
Là, on voit que "rodolphe" reste toujours le sujet central de ce livre mais à côté il y a des autres champs lexicaux qui sont liés. 
>Cette analyse a été pris comme la base pour le graphe de Gephi.

On peut également regrouper par communautés en halos.

![analyse_de_similitudes_commun](https://github.com/soniyabbas/ABBAS_Soniya_LesMysteresdeParis/blob/master/visualisations/analyse_de_similitudes_commun.png)

Et le dernier graphe représente 183 formes qui sont regroupées par communautés et variables choisies (notés en légende) parametré comme _multilevel.community_.

![analyse_de_similitudes_par_chapitre](https://github.com/soniyabbas/ABBAS_Soniya_LesMysteresdeParis/blob/master/visualisations/analyse_de_similitudes_par_chapitre-1.png)

Cette visualisation a été réalisé à partir d'analyse Reinert. Elle était faite à partir l'analyse qu'un seul mot "rodolphe" pour voir des liaisons. 

![analyse_a_partir-dun_mot](https://github.com/soniyabbas/ABBAS_Soniya_LesMysteresdeParis/blob/master/visualisations/analyse_a_partir_dun_mot.png)

### La méthode Reinert

C'est la classification hiérarchique descendante qui permet de regrouper des mots et les réparer sous les thématiques. L'analyse découpe le texte en segment, les regroupe en classe en fonction des composantes (des mots).

Le logiciel nous permet à réaliser des visualisations différentes : 

Cette analyse a regroupé mon corpus dans 6 classes. 
![methode_Reinert_3](https://github.com/soniyabbas/ABBAS_Soniya_LesMysteresdeParis/blob/master/visualisations/me%CC%81thode_Reinert_3.png)

Une autre représentation montre plus profondément le regroupage en fonction des thèmes principaux. On voit sur l'image les mots constitutifs de chaque classe.

![methode_Reinert_4](https://github.com/soniyabbas/ABBAS_Soniya_LesMysteresdeParis/blob/master/visualisations/me%CC%81thode_Reinert_4.png)

Ce sont les visualisations liées à l'analyse factorielle de correspondance mais realisée autreument. Ici on voit 3 classes qui sont ensemble et 3 qui sont liées mais quand même se trouvent à côte. Je peux prendre pour hypothèse que les 3 classes melangées décrivent le corpus principal ; les autres joue le rôle secondaire.

![methode_Reinert_1](https://github.com/soniyabbas/ABBAS_Soniya_LesMysteresdeParis/blob/master/visualisations/me%CC%81thode_Reinert_1.png)

![methode_Reinert_2](https://github.com/soniyabbas/ABBAS_Soniya_LesMysteresdeParis/blob/master/visualisations/me%CC%81thode_Reinert_2.png)

Sources qui ont été utilisés : 
 - [Enseigner l'Histoire par les Données](https://datahist.hypotheses.org/110)
 - [Iramuteq](http://iramuteq.org/Members/pmarchand/faut-il-faire-des-nuages-de-mots)

## Question

Lien vers le fichier [(.md)](https://github.com/soniyabbas/ABBAS_Soniya_LesMysteresdeParis/blob/master/question.md)

## Bonus. Gephi

![resultat_gephi](https://github.com/soniyabbas/ABBAS_Soniya_LesMysteresdeParis/blob/master/visualisations/resultat_analyse_de_similitudes.png)

Le lien vers le fichier gephi avec des relations entre les mots réalisé à la base de l'analyse de similitudes avec 283 formes [(.gephi)](https://github.com/soniyabbas/ABBAS_Soniya_LesMysteresdeParis/blob/master/resultat_analyse_de_similitudes.gephi)
