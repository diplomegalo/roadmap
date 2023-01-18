---
date: 
auteur: Delsaut Pierre-Arnaud 
email: pa.delsaut@wavenet.be
profils:
domaines:
themes:
tags:
---

# Systèmes et langages informatique

Les systèmes et les langages informatiques sont les matériaux de base de la construction d'un bâtiment, car ils viennent littéralement supporter la mise en oeuvre de votre édifice. Chaque ligne de code produite viendra augmenter les fonctionnalités de votre application ou par analogie, la taille de votre immeuble. 

Comme pour tout langage, il y a celui qui le parle et celui qui l'écoute. Chaque langage à sa spécificité, de même que celui qui l'écoute à sa propre manière d'interpréter. Les caractéristiques d'un langage définie ce que l'on peut faire avec, à l'instar du bois qui sera chaud et souple et le béton qui sera froid et ultra résistant. En outre, chaque matériaux à son spécialiste, voir son corps de métier, comme c'est le cas aussi pour les langage informatiques. 

Outre les langage, il y a aussi les systèmes informatiques nécessaires à l'exécution de votre application. Certains sont annexes, par exemple la base de données, d'autres sont des support à l'exécution, comme le système d'exploitation d'un serveur sur lequel l'application est déployée. Pour reprendre l'analogie du bâtiment, on pourrait comparer ça, dans le cadre des services annexe, à la télédistribution, l'accès Internet ou encore à la distribution d'eau et d'éléctricité qui sont utilisés au travers d'une interface comme la box pour la télé et l'internet et les compteurs pour l'eau et l'éléctricité ; ou dans le cadre d'un système de support à la dalle de béton à partir de laquelle une maison sera ériger. Par conséquent, les systèmes vous facilitent la tâche, car ils sont déjà fabriqué et vous n'avez qu'à les utiliser, mais vous pose également des contraintes, car il faut s'y raccorder selon leurs interfaces et il n'est pas possible d'en changer les spécificités (taille, fonctionnalités, etc.). 

## Les langages interprétés et compilés

Dans le cadre d'un langage informatique, il y a deux manières de l'"écouter" : la manière interprétée et la manière compilée. Dans tout les cas, on part d'un fichier contenant le code écrit dans un langage spécifique. 

Dans le cas d'un langage interprété, celui qui "écoute" le langage va directement exécuter les opérations qu'il lit dans le fichier selon sa propre interprétation. Ces langages sont dis "simple", car on appréhende leur implémentation de manière procédurale, c'est-à-dire comme une procédure ou une suite d'action que l'on éxécute, un peu comme une recette de cuisine. Typiquement on retrouve se type de langage dans le cadre des applications frontend de type web et la raison en est  simple : les applications écrite dans un langage interprété ne doivent pas être installée ! Seul l'interpréteur doit l'être et dans le cas des applications web, il s'agit de votre navigateur. Néanmoins ces langages offrent des performances et des fonctionnalités limitées tributaires de l'interpréteur. Imaginez-vous que l'interpréteur de votre recette de pâtes à la bolognaise soit un étudiant fraichement sorti de la rétho, la qualité de la dégustation sera forcément moindre que s'il s'agit d'un chef étoilé.

En ce qui concerne les langages compilé, le fichier va passer par une étape intermédiaire dite de compilation. Cette étape de compilation va produire ce que l'on appel le fichier binaire ou plus simplement le binaire. Ce fichier contient, non plus des lignes de codes, mais une suite de zéros et de uns destiné à être interprété, mais cette fois-ci directement par le processeur au travers du système d'exploitation. Par conséquent, on va directement discuter avec l'ordinateur pour exécuter des commandes et exploiter toutes les ressources de cet ordinateur : l'écran, l'imprimante, le disque dur. Ces langages sont plus complexe, car ils utilisent des fonctionnalités plus avancées et utilise le paradigme de l'orienté objet. Néanmoins, ils offrent des performances nettement meilleurs, on retrouvera donc ce type de langage pour des systèmes backend qui, par nature, devront traiter une grande quantité d'informations.

>À noter qu'auparavant, il existait un désavantage au langages compilé : la portabilité. En effet tous les ordinateurs ne sont pas composés des mêmes processeurs et des mêmes systèmes d'exploitation et par conséquent n'était pas en mesure d'interprété de la même manière tous les binaires. Ce désavantage à aujourd'hui disparu grâce à l'apparition des machines vituelles, qui vont avoir le rôle de traducteur entre un binaire compilé depuis un langage vers l'architecture système de l'ordinateur et son système d'exploitation.

>Le paradigme (ou concept) de l'orienté object conciste à composer les applications de modules, appelé *class* ayant des propriété et des comportements spécifique. Ces classes vont intéragir ensemble. Ainsi une *class* `utilisateur` va `créer` un nouveau `dossier` avec comme `identifiant` : 045/78AE, où la *class* `dossier` aura comme propriété `identifiant` et comme comportement `créer`.

Ci-dessous vous pouvez retrouver la liste des languages les plus utilisés, s'ils sont interprété ou compilé et leurs utilisation backend ou frontend.

| Language   | Int. / Comp. | Back / Front                                           |
| ---------- | ------------ | ------------------------------------------------------ |
| Javascript | Interprété   | Front                                                  |
| HTML/CSS   | Interprété   | Front                                                  |
| SQL        | Interprété   | Back                                                   |
| Python     | Interprété   | Back / Frontend via un le framework PyScript           |
| TypeScript | Interprété   | Frontend (doit être transpilé avant d'être interprété) |
| Java       | Compilé      | Back / Frontend via un framework                       |
| C#         | Compilé      | Back                                                   |
| PHP        | Interprété   | Backend / Frontend                                     |
| Razor      | Compilé      | Frontend                                               | 

## Les systèmes informatiques

Si les languages permettent de façonner une application, les systèmes permettent d'utiliser des fonctionnalités préfabriqués de manière à ne pas réinventer la roue et augmenter l'industrialisation des applications. Pour reprendre le parallèle avec le bâtiment, soit on fabrique un évier, soit on achète un modèle qui répond aux contraintes tant techniques qu'esthétique. 

Dans ce dernier exemple, on se rend bien compte que la production d'évier est suffisament spécifique et difficile que pour ne pas faire le choix de le fabriquer "soit même", mais plutôt de faire appel à des sociétés qui sont spécialisées. C'est la même problématique dans le monde de l'informatique. Certaines fonctionnalités sont à ce point spécifiques que l'on va préférer déléguer la réalisation à des sociétés tiers qui fournissent des produits tout fait que l'on va intégrer à la solution informatique qui est en train d'être implémenté. C'est le cas du stockage des données qui est délégué à un système de base de données qui est intégré à l'application via des connecteurs. 

Vous pouvez retrouver plus d'informations concernant les systèmes dans le chapitre [[les composants et leurs responsabilités]].

## L'exception du low code et du no code

Construire une maison sur mesure ça coute chère, alors certains imagine des solutions pour réduire les coups et fournisse dès lors des solutions "préfabriqué". Que ce soit en kit ou sur plan, l'objectif est de réduire au maximum la phase de façonnage en proposant par exemple des murs préfabriqué (en bois ou en béton), des escaliers préfabriqués voir même des maisons préfabriqués comme le sont les mobil-homes. Ces techniques permettent de réduire drastiquement les coups, car tout à déjà été étudié, et les pièces préfabriquées sont pensées de manière à facilement s'emboiter, par conséquent la main d'oeuvre lié à la construction est fortement réduite.

Il en va de même avec l'informatique, le low code ou le no code respecte le même principe d'élément préfabriqué que l'on peut appeler blocs applicatifs (en référence à un brique), chacun ayant une fonctionnalité plus ou moins élaborée, et qui vont s'imbriquer les uns autres dans un flux ou processus avec des paramétres en entrée et des résultats en sorties, résultats qui pourront être utilisé par d'autres bloc applicatifs et ainsi de suite. 


