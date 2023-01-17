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
---

# L'architecture d'un système

Toute réalisation requiert une étude préalable. Cette étude est généralement réalisé par un architecte voir un groupe d'architecte selon les types de réalisation. Celui-ci va établir un schéma des solutions structurelles à mettre en place en réalisant des plans de constructions décrivant les matériaux, les techniques, les zones et les attributions de chacune d'entre-elles. Pour ce faire, il devra prendre en compte les demandes du client, mais également répondre aux considérations légales et de sécurités, le tout en faisant preuve de bon sense sans jamais dépasser les bugets. 

Il en va de même pour l'élaboration d'une application ou d'un système informatique. En effet, au sein d'une équipe de développement, l'architecte (cf. [[Les métiers de l'IT]]) sera en charge de l'élaboration de la solution d'un point de vue structurel et définira un schéma décrivant les systèmes, leurs intéractions, les technologies, etc. 

L'architecture va définir la découpe d'un système en zone de responsabilité et fonctionnalité. L'objectif est de répondre aux exigences, besoins et contraintes fonctionnelles du projet, mais également d'offrir une structure qui prend en compte des considérations non fonctionnelles telles que les performances, la sécurité. En outre, la structure d'un système doit garantir une certaine pérénité dans le cadre des maintenances évolutives.

>La maintenance évolutive définie toute opération qui consiste à mettre à jour un système ou un composant de celui-ci de manière à le garder opérationnel sans nécessairement ajouter de fonctionnalitée.

## Les enjeux d'une architecture

De la même manière que pour un bâtiment, le principe est d'organiser les choses selon leurs fonctionnalités. Par exemple, la cuisine dans laquelle on retrouvera la taque éléctrique, le frigo et tout l'électro-ménager utile au réalisation culinaire et la salle de bain avec un lavabo et une douche et éventuellement une baignoire.

Un premier enjeux est d'avoir des responsabilités bien définies pour chaque pièce, en ce sens que leurs portés est limité à leurs utilités. En effet, il serait complétement grotesque de placer une taque électrique dans une salle de bain, de même que d'installer une baignoire dans une cuisine. Même dans une chambre d'étudiant où l'espace est particulièrement limité, chaque partie de la chambre est dédié à une fonctionnalité unique : un coin couchage, un coin cuisine, un coin bureau et un coin toilette et hygiène.

Un autre enjeux et de prévoir les services nécessaire et de les intégrer aux zones qui en ont besoin. Par exemple, il est nécessaire de prévoir une arrivée électrique ou de gaz à hauteur des taques de cuisson dans la cuisine, tout en prenant en compte l'obligation de placer un detecteur de fumée non loin pour des raisons de sécurité. Le fait que le détecteur de fumée soit relié à une centrale d'alarme ou qu'il soit une "simple" alarme autonome est également une contrainte à prendre en compte et à intégrer dans les plans. 

Dans le monde de l'informatique, une architecture se construit avec des composants. Chacun d'entre eux se définissent par des responsabilités et des services plus ou moins étendue et sont interconnectés entre-eux.

Habituellement on retrouvera les composants suivants :

- [[les applications frontend]] qui ont la responsabilité de fournir à l'utilisateur une interface qui lui permettra d'utiliser les fonctionnalités du système. Elles auront également la responsabilité de garantir la sécurité grâce au mecanisme d'authentification. 
- [[les applications backend]] qui intègrent la logique et les processus métiers. Selon la complexité des systèmes, le backend peut être divisé en plusieurs sous applications gérant des parties bien distinctes du métier. 
- [[les services bus et messages broker]] qui ont la responsabilité de distribuer l'information entre plusieurs systèmes hétéroclytes. L'information nécessitant quelque fois d'être converti de manière à être compatible entre les différents systèmes.
- [[les systèmes de gestion de base de données]] qui comme le nom l'indique gère les bases de données utile à l'enregistrement et la récupération des données d'un système.

Il existe d'autres systèmes pouvant se retrouver dans une architecture, retrouvez la liste non exhaustive de ces systèmes dans le chapitre [[les composants et leurs responsabilités]].

Consulter le chapitre concernant [[les principes d'implémentation]] pour comprendre les considérations à prendre en compte pour concevoir un système de qualité, fiable et pérène. 

## L'interfacage

Une cabanne, une maison, un immeuble est donc composé de plusieurs zones, elles-même composé de mobilier, d'electro ménager, d'éclairage etc. 

## Les environnements d'exécutions

[[les environnements d'exécutions]]


## Voir aussi

[[les composants et leurs responsabilités]]
[[Les données, formats de données et protocoles]].
[[Les outils]]. 