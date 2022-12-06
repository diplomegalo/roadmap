---
date: 02/12/2022
auteur: Delsaut Pierre-Arnaud
email: diplomegalo@hotmail.com
profils: 
 - management
domaines:
 - developpement
themes:
 - projet
tags:
 - projet
 - langage de programmation
 - application
references:
versions: 
  - date: 03/12/2022
    description : Analogie du bâtiment
---

>[!todo] Review
>---
>- [ ] Analogie du bâtiment
>- [ ] Le type de solution ou livrable
>- [ ] Système et langage
>---
>- [ ] Tags
>- [ ] Orthographe 

# Le bébéa du développement d'un projet IT

## Analogie du bâtiment

La meilleure analogie pour se faciliter la compréhension d'un projet IT, c'est celle d'un projet de construction immobilière. 

Tout y est identique ou presque, même les retards ! Dans le tableau ci-dessous, je fais une comparaison simple entre ce qui est produit concrètement dans le monde du bâtiment et celui de l'IT.

| Construction immobilière | Exemple                                                 | Projet IT                           | Exemple                                                                   |
| ------------------------ | ------------------------------------------------------- | ----------------------------------- | ------------------------------------------------------------------------- |
| Type de construction     | Cabane, garage, maison, immeuble, aeroport              | Type de solution ou Livrable        | Application Web, Web services, application mobiles, client lourd, drivers |
| Outils de construction   | Tournevisse, grue de chantier                           | Outils applicatifs de développement | Git, Azure Devops, Visual Studio, Fiddler                                 |
| Expert du bâtiments      | Plombier, électricien, architecte                       | Technicien et expert IT             | Développeur, architecte, analyste, admin système                          |
| Matériaux du bâtiments   | Bois, briques, béton                                    | Système et langage informatique     | C#, JavaScript, SQL Server, Linux                                         |
| Les plans                | Les plans d'égoutage, éléctrique, de circulation d'aire | Les analyses                        | Les analyses fonctionnelles, techniques ou d'architectures                |

Le type de construction définit se que l'on attend comme livrable. Dans le bâtiment cela peut se traduire par une cabane, un garage, une maison, etc. Chacun de ses types de construction, par sa nature, par sa taille ou encore par sa difficulté, va influer le reste des domaines. En effet, la construction d'une cabane ne nécessite ni les mêmes outils, ni la même expertise ni les mêmes matériaux que la construction d'un immeuble de plusieurs étages dans une zone sismique. 

La reflection est identique pour ce qui est d'un système informatique, c'est le type de solution demandé qui déterminera tous vos choix en terme d'outils, d'expertise et métier de l'informatique et finalement de technologie avec laquelle vous développerez votre application.

## Le type de solution ou livrable

Le type de solution ou le livrable est ce que vous devez développer pour répondre aux besoins exprimé par le client. Généralement, même les plus néophytes d'entre nous connaissent les différents type de système et applicatifs réalisable. Les plus communs seront :

- les applications web, ce sont ces applications offrant des services et fonctionnalités au travers de navigateurs Web tels que Chrome, Edge ou encore Mozilla Firefox. 
- les applications mobiles qui s'exécute sur téléphone portable.
- les clients lourds ou application desktop qui s'installe et s'exécute sur un PC.

Néanmoins derrière ces applications destinées à l'utilisateur finale, d'autres types d'applications ou système peuvent être nécessaires de manière à mettre en place un parc applicatif utile au bon déroulement des processus liés aux fonctionnalités développées dans l'application. Dans ce cadre, on retrouvera par exemple : 

- des services web qui exposent une multitude de fonctionnalités à destination d'applications clientes et qui permettent par exemple de récupérer les données de l'utilisateur à afficher dans une application mobile, ou encore qui retourne les données d'une page HTML à afficher dans un navigateur.
- des services (windows) ou deamon (linux) qui sont des applications hébergées sur un serveur, sans interface et qui réalisent des tâches de fond, donc non initié par une action utilisateur, comme calculer une valeur utile à mettre à jour quotidiennement dans des données comptable par exemple.

Le choix du livrable et des systèmes dépendants nécessaires se fait grâce au concours 

- du client d'une part, qui exprimera l'idée qu'il a du rendu finale de son application, des contraintes fonctionnelles ou non fonctionnelles, par exemple : "l'application doit être accessible sans connexion internet", mais également d'autres types de contraintes telles que le budget ;
- d'autre part, de l'expert technique et de l'analyste, qui prendront en compte les contraintes les plus discriminantes de manière d'avoir un type de solution qui répond aux exigences précités.

Une chose importante à comprendre ici est qu'une solution informatique répond à un besoin et non l'inverse. C'est bien sur base d'une contrainte ou d'une problèmatique qu'un client viendra vous voir avec le besoin d'une solution et c'est en comprenant sa problèmatique qu'il sera possible d'imaginer avec lui une réponse au travers d'écrans, fonctionnalités et processus.

## Les outils applicatifs de développement

Pour construire il faut des outils, certains petits et multi-fonctions comme un marteau pouvant aider dans de nombreuses circonstances, d'autres gigantesques et ultra-spécifique comme une grue de chantier ne servant qu'a une et une seule chose : le transport de charge lourde d'un point à un autre du chantier.

En outre, certains outils sont fabriqués au fil de la construction, par exemple les échaffaudages qui serviront de structure temporaire et dont la taille varira en fonction de l'état d'avancement du projet.

De la même manière, un projet informatique requiert bon nombre d'outils offrant une aide tant dans la gestion, que le suivi et l'élaboration du livrable. Les outils indispensables sont : 

- l'environnement de développement, il s'agit tout bonnement de l'ensemble des appareils et accessoires qui permettront aux techniciens de réaliser le livrable, ça peut aller du clavier, à l'ordinateur ou le gsm portable sur lequel le développeur implémente les fonctionnalités en passant par les instances des applications nécessaire à l'élaboration du système, par exemple une instance de base de données ;
- l'IDE qui est un environnement de développement intégré regroupant 
	- l'éditeur de code qui permet aux développeurs d'écrire le code de manière structurée
	- le compilateur qui permet de construire l'application à livrer, 
	- le débogueur qui permet de parcourrir le code pas à pas lors de l'exécution de l'application de manière à avoir une vue exacte des valeurs circulant à travers le code.
- Le gestionnaire de source
- Le client SQL

D'autres sont moins souvent nécessaire mais peuvent être particulièrement utiles dans certaines circonstances : 
- Client REST Web API
- Fiddler
- l'outils de développement Chromium

## Matériaux du bâtiment

du type langage C#, SQL, Java, JavaScript, PHP => analogie avec des matériaux de base ou peu transformé
du type Framework .NET, Angular => analogie avec des matériaux spéciaux transformé comme le ciment
du type librairie => analogie avec le préfabriqué
du type services Alfresco, Sharepoint => analogie avec des services de TV, Internet, distribution d'eau et éléctricité !! important il faut une interface pour introduire ces dépendances.

 mais également le ciment qui servira de fixation entre les briques et qui sera fabriqué minute au fil du montage d'un mur. A noter que la qualité du ciment est un facteur impactant en ce qui concerne le rendu final de la construction, mais également de la solidité de celle-ci

Chaque matériaux à sa finalité JavaScript = web; C# backend ou backend for frontend ou encore SQL Server, comme le bois, le ciment et l'électricité.

## Système et langage

Sont les matériaux de constructions, car ils viennent littéralement supporté la mise en oeuvre de votre édifice. Chaque ligne de code produite viendra augmenter les fonctionnalités de votre application ou par analogie, la taille de votre bâtiments. 

Chaque langage à ces spécificités, à l'instar du bois qui sera chaud et souple et le béton qui sera froid et ultra résistant.

Pour construire, il faut également des bases. La première de toutes les bases et le système d'exploitation, qui vous permet d'exploiter les fonctionnalité de votre PC. Généralement, les systèmes d'exploitation, ou O.S. pour operating system, seront orienté service, pour vous rendre tous les services dont vous avez besoin comme hébergé votre application pour que les utilisateurs y aient accès, que l'on appel communément serveur.
