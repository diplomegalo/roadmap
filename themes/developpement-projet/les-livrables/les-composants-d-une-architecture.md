---
date: 13/12/2022
auteur: Delsaut Pierre-Arnaud 
email: pa.delsaut@wavenet.com
profils:
  - management
domaines:
  - projet
themes:
  - architecture
tags:  
 - architecture  
 - application 
 - application/frontend 
 - application/backend
 - API
 - protocole
 - data
 - outil/développement
---

# Les composants d'une architecture

## Application Frontend

Généralement, les types applications demandés par un client sont :

- une application web utilisée sur un navigateur web,  
- une application mobile qui s'exécute sur un téléphone portable,  
- une application desktop, appelé également client lourd, qui s'installe et s'exécute sur un ordinateur.

Ces trois types d'applications sont dites *frontend*. Ce terme définit une application qui tourne sur un dispositif informatique exposant une interface graphique utilisée par une personne.

Elles sont subdivisées en deux grandes catégories : les applications *front-office* ou extranet et les applications *backoffice* ou intranet. La différence est fonction de l'utilisateur final et de son besoin. Celles-ci peuvent faire partie d'une seul et même application, ou au contraire être séparées l'une de l'autre de manière à avoir des cycles de développement et de déploiement découplés.

Une application *front office* ou extranet aura pour vocation d'offrir des fonctionnalités à un client qui en aurait besoin. Les fonctionnalités peuvent être d'ordre commercial, comme la vente d'article, ou de services telle que la gestion de mails. Généralement, la portée des fonctionnalités ne concerne que l'utilisateur connecté. Par exemple, lors d'un achat d'article, seul le panier du client est modifié.

Une application *backoffice* ou intranet aura pour fonction de gérer un système ou d'en administrer les informations. Son utilisation est requise par un administrateur, c'est-à-dire une personne clé, définie comme ayant la responsabilité du maintien des données du système. Cette responsabilité va de l'ajout d'une simple information affichée dans le fil d'actualité d'un site web à destination commercial (e-commerce), jusqu'à la mise à jour des quantités de stocks d'un produit ou de données comptables de ce même site. Ces informations sont souvent sensibles et ont une portée qui touche l'ensemble de l'application.

>Un utilisateur dans un projet informatique est communément appelé acteur, il en existe deux types :  
>- l'acteur physique qui désigne une personne vivante qui peut interagir avec une interface graphique,  
>- l'acteur système qui représente un dispositif informatique ou une machine avec laquelle on communique au travers d'interface applicative de programmation (API).

>[!todo]  
>- [ ] Découpe des écrans  
>- [ ] Call to action

### CMS : Custom Management System 

>[!todo]
>- [ ] Umbraco

## Application Backend

En retrait de ces applications *frontend*, il existe d'autres types d'applications ou système, nécessaire au bon fonctionnement de l'application.

L'exemple le plus simple et celui de l'application mobile qui vous permet de faire vos courses alimentaires en ligne. Seule, cette application installée sur un dispositif mobile ne peut contenir tout le catalogue de votre supermarché. Néanmoins, vous devez en disposer de manière à le parcourir lorsque vous naviguez d'un menu à l'autre où lors d'une recherche d'un type de produit en particulier. À ce titre, l'application mobile va utiliser une autre application, qui elle a la responsabilité de lui donner toutes les informations nécessaires en ce qui concerne le catalogue d'article. Cette autre application est hébergée sur un environnement extérieur et est disponible au travers de l'internet. L'application mobile pourra dès lors la requêter en fonction des données dont elle a besoin pour les afficher à l'écran.

Ces applications sont dites *backend* et sont de manière générale des API, c'est-à-dire des Interface de Programmation Applicative. On les trouve communément sous les formes décrites ci-dessous où chacune emploie un protocole, c'est-à-dire un moyen de communiquer, différent.

- Les services web exposant des fonctionnalités via l'internet.  
- Les services (Windows) ou deamon (Linux) qui sont des applications hébergées sur un serveur,  
- Les applications exécutables

Certaines parties développées lors d'un projet IT peuvent n'avoir aucun sens fonctionnel. Il s'agit dès lors de briques applicatives considérées comme des outils participant à l'élaboration de l'application finale.

### Interface de Programmation Applicative ou API

>[!todo]  
>- [ ] API  
>- [ ] REST API  
>- [ ] SOAP API  

## Service Bus et message broker

>[!todo]
>- [ ] EAI / ESB  

## Système de gestion de données

Toute solution informatique produit ou requière des données stockées en mémoire. Selon la quantité de données nécessaires et les associations entre-elles, la gestion de celles-ci sera plus ou moins aisée. A ce titre, il faut faire appel à un Système de Gestion de Données (SGBD) qui aidera aux actions de lecture et écriture de données sur une système de stockage. Ci-dessous, plusieurs moyens de gérer et stocker une donnée.

### Fichier

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

### Base de données

>[!todo]
>- [ ] DB  
>  - [ ] SQL
>  - [ ] NO SQL

## CRM

## GED

>[!todo]    
>- [ ] Alfresco  
>- [ ] Sharepoint  

## ECM

## IDP

>[!todo]  
>- [ ] SSO
>- [ ] AD 
>- [ ] SAML  

## LDAP

## Voir aussi

[[Les données, formats de données et protocoles]].
[[Les outils applicatifs de développement]]. 