---
profils: management
domaines: methodologie
themes: librable
tags:
- solution
- documentation/analyse
- documentation/manuel
- source
---

# Les livrables

Le livrable représente la solution produite et élaborée sur base des demandes du client durant la phase d'implémentation d'un projet. Pour reprendre l'allégorie du bâtiment, il s'agit de la cabane, de la maison, de l'immeuble ou même encore du pont attendu par le maitre d'ouvrage.

Dans le monde de l'informatique, le livrable est ce que le client vous demande de développer pour répondre à ces besoins, c'est-à-dire l'application ou le système, mais également le code source ainsi que la documentation telle que les analyses, le manuel d'utilisation, etc.

L'élaboration d'un livrable se fait grâce au concours :

- du client qui exprime ses besoins et ses contraintes, par exemple : "je veux une application pour mes commerciaux, mais qui doit être accessible sans connexion internet" ;   
- des techniciens et analystes qui prendront en compte les contraintes de manière à implémenter une solution qui répond aux exigences du client.

L'important ici est qu'une solution informatique répond à un besoin et non l'inverse. C'est donc bien sur base d'une contrainte ou d'une problématique qu'un client cherchera une solution et c'est en comprenant sa problématique qu'il sera possible d'imaginer, avec lui, une réponse au travers d'une application.

## La solution

Le terme solution informatique désigne un ensemble de systèmes et d'applications mettant à disposition des fonctionnalités utilisées par un acteur.

> La notion d'acteur fait partie intégrante des méthodologies d'analyses et de suivis de projets et se caractérise par l'utilisateur, qu'il soit humain ou non, qui utilise l'application ou le système.

La différence entre une application et un système se situe au niveau de l'acteur qui l'utilise :

- Une application est destinée à des acteurs physiques, c'est-à-dire des personnes : un guichetier, un agent, un commercial, un administrateur, etc.   
- Un système est destiné à être utilisé par un acteur non physique, par exemple un autre système informatique ou une machine, comme une machine (de chaîne) de production, un ordinateur, un système GPS, une application web, etc.

Selon l'étendue des fonctionnalités, ces systèmes et applications feront partie d'un ensemble complexe où **l'architecture de solution** définit les responsabilités et les interconnexions de chacun d'entre eux. Typiquement, on y retrouvera un **système de gestion de base de données**, **une application frontend** et d'autres **types d'applications** nécessaires à la conception de la solution.

Pour être utilisée, la solution doit être installée dans un **environnement d'exécution**. Cette phase d'installation est appelée le déploiement de l'application. Généralement, une application est déployée sur un serveur web, un ordinateur, un store d'application mobile (Apple, Androïd), une machine, etc.

## La documentation

Durant la vie du projet, des documents seront produits de manière à coucher les exigences "sur papier" et offrir une aide au suivi du projet en les validant. Dans ce cadre, il existe des méthodologies cadrant l'édition d'un document, notamment en ce qui concerne l'élaboration des analyses.

### Les analyses

Ces analyses entrent dans le cadre du développement et du **suivi de projet**, où il est possible, sur base de celle-ci, d'organiser les développements et par conséquent de suivre l'évolution du projet et de donner les indications fonctionnelles (comment ça fonctionne) aux développeurs de manière à les implémenter.

En préambule d'un projet **un cahier des charges** ou **une analyse métier** sera édité de manière à connaitre les besoins du client. Ce document permet de se rendre compte de la portée du projet et d'avoir un aperçu des fonctionnalités attendues sans rentrer dans le détail de l'implémentation. C'est également durant cette phase que les processus métiers seront analysés afin de comprendre la temporalité, les règles et les logiques ainsi que les interactions entre les différents acteurs.

>La temporalité d'un processus fait référence au temps qu'un processus peut prendre avant qu'il ne termine. Certains processus peuvent prendre plusieurs jours et comprendre des échanges entre plusieurs acteurs.

C'est sur base de cette analyse qu'une première estimation sera faite, de même que le choix des technologies à utiliser pour implémenter la solution informatique.

S'en suivra une analyse plus détaillée de chacun des écrans et fonctionnalités de la solution : **l'analyse fonctionnelle**. Celle-ci permettra de donner des priorités dans l'ordre d'implémentation des fonctionnalités, de même qu'organiser des livraisons intermédiaires de la solution regroupant un sous-ensemble suffisamment autonome de fonctionnalités pouvant être utilisées.

### Les manuels d'utilisation

Dans certains cas, un manuel d'utilisation de l'application livrée au client peut être nécessaire. Ce manuel répond aux questions d'utilisation en montrant les étapes, écran par écran, d'un processus pour parvenir à utiliser les fonctionnalités de l'application.

## Les sources

Les sources désignent le code édité pendant le projet. Elles font partie de la propriété intellectuelle de l'entreprise, car elles implémentent les règles et la logique métier utile au fonctionnement de l'application. Par conséquent, elles font également partie du livrable remis au client en fin de projet. Néanmoins, la maintenance évolutive du projet étant, en règle générale, de la responsabilité de l'éditeur, celui-ci en garde une copie correspondant à l'application déployée.

>La maintenance évolutive concerne la phase post-livraison de la version finale d'une solution. Cette phase consiste à garantir la pérennité de la solution en cas de bug ou de faille de sécurité et d'apporter d'éventuelles évolutions mineures.

## Suivants

- [Les outils de développement et suivi de projet](outils.md)
- [Les systèmes et langages informatiques](langages-et-systemes.md)
- [L'architecture d'un système](architecture.md)
