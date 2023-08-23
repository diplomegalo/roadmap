---
profils: management
domaines: methodologie
themes: langage
tags:
 - langage/compile
 - langage/interprete
 - low-code
 - no-code
---

# Langages et systèmes informatiques

Les systèmes et les langages informatiques sont les matériaux de base de la construction d'un bâtiment, car ils viennent littéralement supporter la mise en oeuvre de votre édifice. Chaque ligne de code produite viendra augmenter les fonctionnalités de votre application ou par analogie, la taille de votre immeuble. 

Comme pour tout langage, il y a celui qui le parle et celui qui l'écoute. Chaque langage à sa spécificité, de même que celui qui l'écoute à sa manière de l'interpréter. Les caractéristiques d'un langage définie ce que l'on peut faire avec, à l'instar du bois qui sera chaud et souple et le béton qui sera froid et ultra résistant. En outre, chaque matériau à son spécialiste, voir son corps de métier, comme c'est le cas pour le domaine informatique. 

En plus des langages comme matériaux de base, il y a aussi les systèmes informatiques. Certains sont annexes, comme la base de données, d'autres sont des supports, comme le système d'exploitation. Pour reprendre l'analogie du bâtiment, les services annexes seraient comparable, à la télédistribution, l'accès Internet ou encore à la distribution d'eau et d'électricité. Chacun de ces services est utilisé au travers d'une interface : la box pour la télé, et les compteurs pour l'eau ou l'électricité. De même, pour ce qui concerne les systèmes de support, ils seraient comparables aux matériaux fabriqués en dehors du chantier, comme le béton, qui arrive tout fait de manière à être posé pour garantir la base du bâtiment : la chape. De manière intuitive, on se rend compte que les systèmes vous facilitent la tâche, car ils sont déjà fabriqués et sont prêts à être utilisés, mais, d'un autre point de vue, ceux-ci vous posent également des contraintes, car il faut s'y raccorder selon leurs interfaces et il n'est pas possible d'en changer ou d'étendre les spécificités (la taille, les fonctionnalités, etc.).

## Les langages interprétés et compilés

Dans le cadre d'un langage informatique, il y a deux manières de l'"écouter" : la manière interprétée et la manière compilée.

Dans le cas d'un langage interprété, celui qui "écoute" le langage va directement exécuter les opérations selon son interprétation. Ces langages sont dits "simple", car on appréhende leur implémentation de manière séquentielle (du haut vers le bas), c'est-à-dire comme une procédure ou une suite d'action que l'on exécute, ou encore comme une recette de cuisine. Typiquement, on retrouve ce type de langage dans le cadre des applications frontend de type web et la raison en est simple : les applications écrites dans un langage interprété ne doivent pas être installées ! Seul l'interpréteur doit l'être et dans le cas des applications web, il s'agit du navigateur. Néanmoins ces langages offrent des performances et des fonctionnalités limitées, tributaires de l'interpréteur. Imaginez-vous que l'interpréteur de votre recette de pâtes à la bolognaise est un étudiant fraichement sorti de rhétorique, la qualité de la dégustation sera forcément moindre que s'il s'agit d'un chef étoilé.

En ce qui concerne les langages compilés, il existe une étape intermédiaire dite de compilation. Celle-ci va produire ce que l'on appelle le fichier binaire. Celui-ci contient, non plus des lignes de codes, mais une suite de zéros et de uns, destinée à être interprété, cette fois-ci, directement par le processeur de la machine (au travers du système d'exploitation). Par conséquent, on va directement discuter avec l'ordinateur pour exécuter des commandes et exploiter toutes les ressources de cet ordinateur : l'écran, l'imprimante, le disque dur, etc. Ces langages sont plus complexes, car ils utilisent des fonctionnalités plus avancées et utilisent notamment le paradigme de l'orienté objet. En outre, ils offrent des performances nettement meilleures. On retrouvera donc ce type de langage pour des systèmes backend qui, par nature, devront traiter une grande quantité d'informations dans un laps de temps restreint.

>À noter qu'auparavant, il existait un désavantage aux langages compilé : la portabilité. En effet tous les ordinateurs ne sont pas composés des mêmes processeurs. Par conséquent, ceux-ci n'étaient pas en mesure d'"écouter le code" de la même manière. Ce désavantage a aujourd'hui disparu, grâce à l'apparition des machines virtuelles, qui servent littéralement de traducteurs entre les commandes envoyées par l'application, et l'exécution de celle-ci dans l'architecture système de l'ordinateur.

>Le paradigme (ou concept) de l'orienté object consiste à composer les applications de modules autonomes ayant des propriétés et des comportements spécifiques. Ces modules, appelé `class`, vont interagir ensemble. Ainsi une *class* `utilisateur` va `créer` un nouveau `dossier` avec comme `identifiant` : 045/78AE, où la *class* `dossier` aura comme propriété l'`identifiant` et comme comportement `créer`.

Ci-dessous vous pouvez retrouver la liste des langages les plus utilisés, s'ils sont interprétés ou compilés et leurs utilisations backend ou frontend.

| Language   | Int. / Comp. | Back / Front                                           |
| ---------- | ------------ | ------------------------------------------------------ |
| Javascript | Interprété   | Frontend / Backend (via next.js)                          |
| HTML/CSS   | Interprété   | Frontend                                                  |
| SQL        | Interprété   | Backend                                                   |
| Python     | Interprété   | Backend / Frontend via un le framework PyScript           |
| TypeScript | Interprété   | Frontend (doit être transpilé avant d'être interprété) |
| Java       | Compilé      | Backend / Frontend via un framework                       |
| C#         | Compilé      | Backend                                                   |
| PHP        | Interprété   | Backend / Frontend                                     |
| Razor      | Compilé      | Frontend                                               | 

## Les systèmes informatiques

Si les langages permettent de façonner une application, les systèmes permettent eux d'utiliser des fonctionnalités préfabriquées de manière à ne pas réinventer la roue et augmenter l'industrialisation des applications. Pour reprendre le parallèle avec le bâtiment, soit on fabrique un évier, soit on en achète un modèle qui répond aux contraintes tant techniques qu'esthétiques. 

Dans ce dernier exemple, on se rend bien compte que la production d'évier est suffisamment spécifique et difficile que pour ne pas faire le choix de le fabriquer "soit même", mais au contraire, de faire appel à des sociétés qui sont spécialisées dans ce domaine. C'est la même problématique dans le monde de l'informatique. Certaines fonctionnalités sont à ce point spécifiques et complexes, que l'on va préférer déléguer la réalisation à des sociétés tierces, qui fournissent des produits tout faits, que l'on va intégrer à la solution informatique. C'est par exemple le cas du système de gestion de base de données (SGBD), à qui est déléguée la gestion des données produite et manipulé par une application. 

## L'exception du low code et du no code

Construire une maison sur mesure ça coute cher, alors certains imaginent des solutions pour réduire les coûts et fournissent dès lors des solutions "préfabriqué". Que ce soit en kit ou sur plan, l'objectif est de réduire au maximum la phase de façonnage en proposant par exemple des murs préfabriqués (en bois ou en béton), des escaliers préfabriqués, voir même des maisons préfabriquées comme le sont les mobil-homes. Ces techniques permettent de réduire drastiquement les coûts, car tout a déjà été étudié, et les pièces préfabriquées sont pensées de manière à facilement s'emboiter, par conséquent la main-d'œuvre liée à la construction est fortement réduite.

Il en va de même avec l'informatique, le low code ou le no code respecte le même principe d'élément préfabriqué, que l'on peut appeler blocs applicatifs (en référence à une brique), chacun ayant une fonctionnalité plus ou moins élaborée, et qui vont s'imbriquer les un aux autres, dans un flux ou processus, avec des paramètres en entrée et des résultats en sorties, résultats qui pourront être utilisés par d'autres blocs applicatifs et ainsi de suite. 

Néanmoins ce principe comporte des limitations telles qu'il n'est pas possible de sortir du cadre de ce qui a été étudié à la base et par conséquent, ne pas correspondre aux besoins du projet. 

## Suivants

- [L'architecture d'un système](architecture.md)
