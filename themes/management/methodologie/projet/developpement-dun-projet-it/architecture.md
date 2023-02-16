---
profils:
  - management
domaines:
  - projet
themes:
  - architecture
tags:
---

# L'architecture d'un système

Toute réalisation requiert une étude préalable. Dans le cadre de la construction d'un bâtiment, cette étude est généralement réalisé par un architecte ou un groupe d'architecte selon les types de réalisations. Celui-ci va établir un schéma des solutions structurelles à mettre en place en réalisant des plans de constructions décrivant les matériaux, les techniques, les zones et les attributions de chacune d'entre-elles. Pour ce faire, il devra prendre en compte les demandes du client, mais également répondre aux considérations légales et de sécurités, le tout en faisant preuve de bon sense sans jamais dépasser les bugets. 

Il en va de même pour l'élaboration d'une application ou d'un système informatique. En effet, au sein d'une équipe de développement, l'architecte sera en charge de l'élaboration de la solution d'un point de vue structurel et définira un schéma décrivant les systèmes, leurs intéractions, les technologies, etc. 

L'architecture va découper le système en zone de responsabilité et fonctionnalité. L'objectif est de répondre aux exigences, besoins et contraintes fonctionnelles du projet, mais également d'offrir une structure qui prend en compte les considérations non fonctionnelles telles que les performances et la sécurité. En outre, la structure d'un système doit garantir une certaine pérénité dans le cadre des maintenances évolutives futures.

## Les enjeux d'une architecture

De la même manière que pour un bâtiment, le principe est d'organiser les choses selon leurs fonctionnalités. Par exemple, une cuisine sera composé de d'une taque éléctrique, d'un frigo et de tout l'électro-ménager utile aux réalisations culinaires, tandis que la salle de bain sera, elle, composée d'un lavabo et d'une douche et éventuellement d'une baignoire.

Un premier enjeux est d'avoir des responsabilités bien définies pour chaque pièce, en ce sens que leurs portés est limité à leurs utilités. En effet, il serait complétement grotesque de placer une taque électrique dans une salle de bain, de même que d'installer une baignoire dans une cuisine. Même dans une chambre d'étudiant où l'espace est particulièrement limité, chaque partie de la chambre est dédié à une fonctionnalité unique : un coin couchage, un coin cuisine, un coin bureau et un coin toilette et hygiène.

Un autre enjeux et de prévoir les services nécessaires et de les intégrer aux zones qui en ont besoin. Par exemple, il est nécessaire de prévoir une arrivée électrique ou de gaz à hauteur des taques de cuisson dans la cuisine, tout en prenant en compte l'obligation de placer un detecteur de fumée non loin, pour des raisons de sécurité. Le fait que le détecteur de fumée soit relié à une centrale d'alarme ou qu'il soit une "simple" alarme autonome est également une contrainte à prendre en compte et à intégrer dans les plans. 

Dans le monde de l'informatique, une architecture se construit avec des composants. Chacun d'entre eux se définissent par des responsabilités et des services plus ou moins étendue et sont interconnectés entre-eux.

Habituellement on retrouvera les composants suivants :

- **les applications frontend** qui ont la responsabilité de fournir à l'utilisateur une interface qui lui permettra d'utiliser les fonctionnalités du système. Elles auront également la responsabilité de garantir la sécurité grâce au mecanisme d'authentification. 
- **les applications backend** qui intègrent la logique et les processus métiers. Selon la complexité des systèmes, le backend peut être divisé en plusieurs sous applications gérant des parties bien distinctes du métier. 
- **les services bus et messages broker** qui ont la responsabilité de distribuer l'information entre plusieurs systèmes hétéroclytes. L'information nécessitant quelque fois d'être converti de manière à être compatible entre les différents systèmes.
- **les systèmes de gestion de base de données** qui, comme le nom l'indique, gère les bases de données utile à l'enregistrement et la récupération des données.

Il existe d'autres systèmes pouvant se retrouver dans une architecture, retrouvez la liste non exhaustive de ces systèmes dans le chapitre **les composants et leurs responsabilités**.

## Les (inter) connexions

Prenons l'exemple de l'installation d'un chauffage au gaz dans une maison. Nous avons plusieurs systèmes et plusieurs sources, comme la chaudière et les radiateurs de type convecteur en guise de système et l'eau et le gaz en terme de source. 

Le premier système : la chaudière, va prendre en entrée (input) l'eau et le gaz et aura comme responsabilité de chauffer l'eau par le biai de la combustion du gaz. Le deuxième système : le radiateur, va recevoir l'eau chaude et diffuser la chaleur par rayonnement. Ces deux systèmes, on des entrées : le gaz, l'eau et l'eau chaude et on des sorties l'eau chaude et la chaleur. 

Pour permettre d'acheminer le gaz et l'eau et de faire parvenir l'eau chaude et la chaleur, les systèmes devront être inter-connecté l'un à l'autre. Ainsi le professionel, en l'occurence le chauffagiste, va utiliser plusieurs type de tuyaux dont les caractéristiques sont définies (normalisées), adaptés à leurs fonction : acheminer du gaz sous pression pour l'un et acheminer de l'eau froide ou chaude sous pression pour l'autre.

Un système informatique va avoir les mêmes contraintes : comment faire transiter les données en entrée et en sortie des systèmes ? Si pour le batiments les caractéristiques porteront sur la section (le diamètre) et la matière des tuyaux utilisés, les concepts informatique de normalisation de la données seront définis par le **protocole**, l'**encodage des données** et le **format de données**.

Un protocole

l'encodage des données

Le format de données 
>- [ ] L'encodage
>	- [ ] UTF-8
>	- [ ] ASCII
>- [ ] Format de données
>	- [ ] XML
>	- [ ] Json

De nombreux types d'encodages sont apparus au cours du temps, intégrant de plus en plus d'alphabet dans leur définitions. Aujourd'hui l'ASCII est un encodage largement répandu, mais il n'est pas le seul.

## Les environnements d'exécutions

[[les environnements d'exécutions]]


## Voir aussi

[[les composants et leurs responsabilités]]
[[Les données, formats de données et protocoles]].
[[Les outils]]. 
