# Système de gestion de données

Toute solution informatique produit ou requière des données stockées en mémoire. Selon la quantité de données nécessaires et les associations entre-elles, la gestion de celles-ci sera plus ou moins aisée. A ce titre, il faut faire appel à un Système de Gestion de Données (SGBD) qui aidera aux actions de lecture et écriture de données sur une système de stockage. Ci-dessous, plusieurs moyens de gérer et stocker une donnée.

## Fichier

Un fichier consiste en un espace mémoire réservé sur un système de stockage dans lequel on peut y inscrire des données. La taille du fichier est définie par la quantité d'informations.

C'est un peu comme une feuille de papier : on y écrit facilement des informations, mais dès lors qu'on beaucoup de chose à y écrire et selon une structure qui n'est pas de gauche à droite et de haut en bas, ça devient compliqué. 

Concrètement, immaginez-vous devoir écrire dans un cahier, tous les informations concernant vos clients, l'historique de leurs achats et tout votre catalogue produit. Si vous avez peu de client, peu de produit et peu d'achat par jour, la solution papier est envisageable. Dans le cas, contraire cela va vite devenir ingérable. 

Conclusion, un fichier est tout à fait adapté pour contenir de petites quantités d'informations organisées de manière simple. Généralement, on utilisera des fichiers pour transférer ou mettre à disposition un sous-ensemble de données, comme une liste de numéro de client à importer dans un système, ou un text à envoyer par email dans lequel certaines zone doivent être remplacer par un nom, une date ou un autre type de valeur. 

Les types de fichiers sont divers : 
- les fichiers text (.txt) contenant du text brut,
- les fichiers *comma separated values* (.csv) qui eux aussi contiennent du text brut, mais dans un format particulier permettant de les organiser en lignes et en colonnes dans un tableau,
- les fichiers Excel (.xlsx) qui contiennent les données textes contenu dans le tableur, mais également bon nombre d'autres informations : formule, onglet, police, etc,
- les fichiers image (.png, .jpg, .svg).

Chaque fichier à son encodage propre. Par exemple, un fichier contenant du text peut être encodé selon les normes ASCII ou UTF-8.

>L'encodage est inhérent au format binaire de l'informatique. Il définit la correspondance entre un caractére et sa représentation en suite de 0 et de 1 sur un nombre définit de bits. Consulter le chapitre concernant [[Les données, formats de données et protocoles]] pour en savoir plus.

>Il ne faut pas confondre le format d'un fichier et l'encodage. Le format définit la manière dont les données sont organisées au sein du fichier. 

## Base de données

>[!todo]
>- [ ] DB  
>  - [ ] SQL
>  - [ ] NO SQL
