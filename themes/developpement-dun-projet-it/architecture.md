---
profils: management
domaines: projet
themes: architecture
tags:
 - connexion/protocol
 - data//encodage
 - data/format
 - frontend
 - backend
 - service-broker
 - sgbd
---

# L'architecture d'une solution informatique

Toute réalisation requiert une étude préalable. Dans le cadre de la construction d'un bâtiment, cette étude est réalisée par un bureau d'architecte. Celui-ci va établir un schéma des solutions structurelles à mettre en place, en réalisant des plans de constructions, décrivant les zones et attributions de chacune d'entre-elles, ainsi que les matériaux et les techniques utilisées pour leur élaboration. Pour ce faire, il devra prendre en compte les demandes du client, mais également répondre aux considérations légales et sécuritaires, le tout en faisant preuve de bon sens, sans jamais dépasser les budgets. 

Il en va de même pour l'élaboration d'une application ou d'un système informatique. Au sein d'une équipe de développement, l'architecte sera en charge de l'élaboration de la solution d'un point de vue structurel et définira un schéma décrivant les systèmes et leurs interactions, ainsi que les technologies utilisées dans ce cadre. Son travail consistera donc à découper le système en zone de responsabilité et de fonctionnalité ; l'objectif étant de répondre aux exigences, besoins et contraintes fonctionnelles du projet, mais également d'offrir une structure qui prend en compte les considérations non fonctionnelles, telles que les performances et la sécurité. En outre, la structure d'un système doit garantir une certaine pérennité dans le cadre des maintenances évolutives futures.

## Les enjeux d'une architecture

De la même manière que pour un bâtiment, le principe est d'organiser les choses selon leurs fonctionnalités. Par exemple, une cuisine sera composée d'une taque électrique, d'un frigo et de tout l'électroménager utile aux réalisations culinaires, tandis que la salle de bain sera, elle, composée d'un lavabo et d'une douche et éventuellement d'une baignoire destiné à l'hygiène de soi.

Un des premiers enjeux est d'avoir des responsabilités bien définies pour chaque pièce, de manière à ce que leurs fonctionnalités soient limitées à leurs utilités. En effet, il serait complètement grotesque de placer une taque électrique dans une salle de bain, de même que d'installer une baignoire dans une cuisine. Même dans une chambre d'étudiant où l'espace est particulièrement limité, chaque partie de la chambre est dédiée à une fonctionnalité unique : un coin couchage, un coin cuisine, un coin bureau et un coin toilette et hygiène.

Un autre enjeu et de prévoir les services nécessaires et de les intégrer aux zones qui en ont besoin. Par exemple, il est nécessaire de prévoir une arrivée électrique ou de gaz à hauteur des taques de cuisson dans la cuisine, tout en prenant en compte l'obligation de placer un détecteur de fumée non loin, pour des raisons de sécurité. Le fait que le détecteur de fumée soit relié à une centrale d'alarme ou qu'il soit un "simple" dispositif autonome est également une contrainte à prendre en compte et à intégrer dans les plans. 

Dans le monde de l'informatique, une architecture se construit avec des composants définis par des responsabilités et des services plus ou moins étendus.

Habituellement on retrouvera les composants suivants :

- **[les applications frontend](./architecture/frontend.md)** qui ont la responsabilité de fournir à l'utilisateur une interface qui lui permettra d'utiliser les fonctionnalités du système. Elles auront également la responsabilité de garantir la sécurité grâce au mécanisme d'authentification. 
- **[les applications backend](./architecture/backend.md)** qui intègrent la logique et les processus métiers. Selon la complexité des systèmes, le backend peut être divisé en plusieurs sous-applications gérant des parties bien distinctes du métier. 
- **les services bus et messages broker** qui ont la responsabilité de distribuer l'information entre plusieurs systèmes hétéroclites. L'information nécessitant quelquefois d'être converti de manière à être compatible entre les différents systèmes.
- **[les systèmes de gestion de base de données](./architecture/sgbd.md)** qui, comme le nom l'indique, gère les bases de données utiles à l'enregistrement et la récupération des données.

## Les (inter) connexions

Prenons l'exemple de l'installation d'un chauffage au gaz dans une maison. Nous avons plusieurs systèmes et plusieurs sources. Le premier système : la chaudière. Elle va prendre en entrée l'eau et le gaz et aura comme responsabilité de chauffer l'eau par le biais de la combustion du gaz. Le deuxième système : le radiateur. Il va recevoir l'eau chaude et diffuser la chaleur par rayonnement.

Pour permettre d'acheminer le gaz et l'eau à la chaudière, et l'eau chaude aux radiateurs, les systèmes devront être interconnectés. Ainsi le professionnel, en l'occurrence le chauffagiste, va utiliser plusieurs types de tuyaux pour connecter les systèmes entre eux. Ceux-ci auront des caractéristiques définies et normalisées, de manière à pouvoir répondre au mieux à leurs fonctions, c'est-à-dire, acheminer du gaz sous pression pour l'un et acheminer de l'eau froide ou chaude pour l'autre.

Un système informatique va devoir répondre aux mêmes contraintes : comment faire transiter les données entre les systèmes ? Si pour le bâtiment les caractéristiques des connexions sont définies par une section et un type de matériau ; pour l'informatique elles sont définies par un **protocole**, un **encodage des données** et un **format de données**.

### Les protocoles

De la même manière qu'il existe des protocoles sociaux où avant de discuter avec une personne, on la salue, il existe des protocoles informatiques qui vont définir les échanges entre les systèmes. Un exemple de protocole connu est l'HTTP, qui définit comment un client (navigateur) va interroger un serveur web et comment celui-ci lui répondra. De manière générale, la définition d'un protocole défini les échanges notamment en termes :

- de modèle : si tu me demandes de me présenter, alors je te donnerais, mon nom, mon prénom, mon âge, mais pas mon adresse et pas mon numéro de téléphone;
- de définition de contenu : si tu me dis au revoir par téléphone, je ne m'attends plus à ce que l'on discute ensemble et je couperai la communication;
- d'ordre : avant de me donner le contenu de ton message, je m'attends à ce que tu me dises : "bonjour" et je te répondrai : "bonjour, en quoi puis-je vous aider ?".

### L'encodage des données

De la même manière que l'être humain utilise un alphabet pour représenter des lettres, l'informatique va définir des encodages pour représenter des caractères. 

Un alphabet définit un nombre fini de représentations possibles de caractères. Ainsi l'alphabet français, hors accentuation, ponctuation, majuscule et minuscule, sera constitué de 27 lettres, tandis que le grec en sera composé de 24. Il en va de même pour les encodages : chacun d'entre eux définit un nombre limité de représentations de lettres, de ponctuations, de caractères spéciaux et même pour certains d'emojis. 

Ce nombre de caractères représentable va avoir une incidence directe sur la taille des messages. Pour comprendre ce point, il faut se souvenir que l'informatique est une suite de 0 et de 1 : un bit. Avec un 0 et un 1, je peux représenter deux caractères, où 1 sera la lettre A et 0 la lettre B. Autrement dit, pour utiliser un alphabet de deux caractères, j'ai besoin de 1 bit. L'encodage ASCII contient lui théoriquement 128 caractères différents. Pour les représenter, j'ai donc besoin de 2^7 bit. En revanche, l'encodage l'UTF8 peut en contenir 4 398 046 511 104 et dans ce cas j'ai besoin de 2^24 bit. Imaginez-vous maintenant devoir placer chacun de ces bits sur une table, l'espace nécessaire pour représenter un caractère encodé en UTF-8 sera largement plus grand que celui nécessaire pour l'ASCII. Par conséquent, l'encodage choisi va avoir une influence directe sur la taille des messages. Partant de ce constat, on peut facilement se rendre compte que, s'il est très couteux, en termes de performance ou de stockage, de faire passer des messages volumineux, on préfèrera utiliser un encodage qui prend moins de place, mais qui dès lors, contiendra moins de caractères représentables.

### Le format de données

Le format des données va définir l'organisation des données entre elles afin d'être présenté de manière compréhensible pour un système. Généralement une information est composée de données et de métadonnées, où la donnée est la valeur, tandis que la métadonnée est le contexte qui donne sens à la valeur. En effet, si une donnée à la valeur 1, celle-ci pourrait correspondre à une quantité, un poids, une heure, un âge. Sans métadonnée, la donnée seule n'a pas de sens. Il existe autant de formats de données qu'il est possible d'en définir : c'est infini. Néanmoins, il existe des formats normalisés dont l'exploitation est facilitée grâce à [des librairies de code](outils/outils-developpement.md#les-frameworks-et-les-librairies) déjà implémentées. Ci-dessous, une liste non exhaustive des formats normalisés utilisés fréquemment pour échanger des informations entre systèmes.

- Le **CSV**, pour _Comma Separted Value_. Ce type de format est notamment utilisé pour exporter des données stockées sous forme de tableau.
- L'**XML**, pour _eXtended Markup Language_. Ce format est organisé sous forme de balises (markup) contenant l'information. Il est également possible d'ajouter des attributs de manière à étendre le contexte d'une balise. Ci-dessous un exemple de fichier XML contenant la signalétique d'une personne. L'XML a la particularité de pouvoir être validé en termes de format par le biais d'un fichier XSD (contenant la définition de celui-ci).
```xml
<prenom genre="f">Sarah</prenom>
<nom>Vantems</nom>
<adresse>
  <rue>Clos du Réculet</rue>
  <numero>4</numero>
  <boite></boite>
  <codePostal>4583</codePostal>
  <ville>Tarmegnies</ville>
  <pays>Kremarie</pays>
</adresse>
```
- Le **JSON**, dont se sont les caractères qui définissent l'organisation des données avec, par exemple, les caractères `{` et `}` qui définissent le début et la fin d'une donnée. Ci-dessous, un exemple de fichier JSON contenant les mêmes informations que précédemment.
```json
{
  "prenom": {
    "genre": "f",
    "value": "Sarah"
  },
  "nom": "Vantems"
  "adresse": {
    "rue": "Clos du Réculet",
    "numero": 4,
    "codePostal": 4583,
    "ville": "Tarmegnies",
    "pays": "Kremarie"
  }
}
```
