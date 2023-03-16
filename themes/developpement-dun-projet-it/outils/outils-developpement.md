---
profils: management
domaines: methodologie
themes: outils-developpement
tags:
 - outils/developpement/ide
 - outils/developpement/client-sql
 - outils/developpement/client-webapi
 - outils/developpement/framework
 - outils/developpement/librairies
---

# Les outils de développement

## Les outils applicatifs et systèmes

L'ensemble des outils applicatifs requis pour développer une solution informatique sont l'environnement de développement, l'IDE et le gestionnaire de sources. Ensemble, ils forment la base nécessaire au développeur pour élaborer un système informatique.

L'environnement de développement est l'ensemble des appareils et accessoires qui permettront aux techniciens de réaliser le livrable. Ça peut aller du clavier à l'ordinateur, en passant par le GSM sur lequel installer et tester une application mobile. On y retrouve également les systèmes et applications, comme pourrait l'être l'OS d'un PC ou d'un appareil mobile (Windows, Linux, Androïd, OSX, etc.).

L'IDE, quant à lui, est un outil de développement intégré regroupant :

- l'éditeur de code, qui permet aux développeurs d'écrire les sources,
- le compilateur, qui permet de vérifier la syntaxe de ce qui est écrit et de construire l'application,
- le débogueur, qui permet de parcourir le code pas à pas, lors de l'exécution de l'application, de manière à avoir une vue exacte des valeurs circulant à travers celui-ci et le cas échéant de le corriger en cas de bug.

Finalement, le gestionnaire de source, qui permet de centraliser les lignes de codes produites par les développeurs, mais également de les fusionner et d'en gérer l'historique de versions. En outre, les gestionnaires de sources vont offrir des services supplémentaires, tels que la maintenance automatique du code et le déploiement automatique des applications (cf. **les environnements d'exécutions**), qui sont respectivement nommés par les termes anglais _Continuous Integration_ et _Continuous Deployement_.

A cela peuvent s'ajouter d'autres outils particulièrement utiles comme : 
- l'outil de développement du navigateur Web, qui permet notamment de 
 - débugger l'exécution du code JavaScript directement depuis le navigateur,
 - de récupérer les informations stockées en local de la machine,
 - de visionner les différents messages et fichiers qui ont été échangés avec un serveur ;
- un client Web API, nécessaire pour interroger un service Web distant ;
- un client SQL, utile pour interroger une base de données.

### Les IDE

Les IDE sont des éditeurs de code. Ils permettent aux développeurs de concevoir l'application, mais également de la "construire". Par conséquent, ils sont fortement liés à la technologie ou au langage de programmation.

Une fois le code édité, le développeur va passer par une phase de vérification de celui-ci, comme on pourrait le faire communément avec un vérifieur orthographique. Il s'agit de la compilation. Cette étape a comme finalité de "construire" un binaire, autrement dit l'application ou le système. Ce binaire exécutable est ensuite déployé dans **les environnements d'exécutions**, c'est-à-dire là où s'exécute l'application. Ces binaires peuvent avoir différentes extensions de fichier comme .dll, .exe, .war, .jar, etc.

Les IDE les plus connus sont 
- Visual Studio pour tous les langages lié à .NET, 
- Eclipse pour le Java, 
- PHP Storm pour le PHP.  

### Les clients SQL

Les bases de données permettent, entre autres, d'enregistrer, de modifier, de supprimer et de lire des données. Pour accéder à celles-ci, les applications possèdent un connecteur par lequel ils envoient des commandes de traitement des données, appelées _Query_. Les requêtes de traitement ou de récupération de données sont écrites en langage SQL (Structured Query Language). 

Le client SQL est un programme qui permet d'accéder à des bases de données et d'éditer des requêtes SQL. Ce client va donc permettre d'interagir directement avec la base de données, sans attendre que l'application soit complètement développée. De cette manière, il sera possible de récupérer ou préparer des données, par exemple dans le cadre d'exécution de tests.

### Les clients Web API

Généralement une application fait partie d'un écosystème plus vaste, où d'autres systèmes appelés services ou API fournissent, au travers d'une interface, une multitude de fonctionnalités. Dans le cadre de services Web ou Web API, cette interface est disponible au travers du protocole HTTP.

>Un protocole est la définition du moyen de communication entre deux systèmes. Un exemple de protocole informatique connu de tous est l'HTTP. Il définit comment un client va interroger un serveur Web et comment celui-ci va répondre. Ceci va de pair avec la notion de langage et d'interaction sociale qui définit que lorsque l'on pose une question à une personne étrangère, on le salue dans un premier temps, on se présente ensuite, puis seulement on lui demande s'il est disponible et en fonction de sa réponse, on lui pose notre question.

Le client Web API permet de se connecter à un serveur de la même manière qu'une application le ferait, afin de recevoir la réponse brute, sans en interpréter le contenu et par conséquent de le vérifier, que ce soit en termes de format ou de données. Ce type de client est très utile dans le cadre de tests, car avant même d'avoir implémenté l'application, le développeur est en mesure de créer des requêtes et d'en analyser les résultats. Ceci lui permettant d'appréhender l'implémentation qu'il devra réaliser pour traiter les réponses d'une requête HTTP.

## Les frameworks et les librairies

Généralement confondus, ces deux termes définissent des concepts pourtant différents. Les librairies sont des bibliothèques, une sorte de boite à outils réutilisable en fonction du besoin. Tandis que les frameworks sont des structures de base, qui vont permettre de vous faciliter la tâche en vous offrant des solutions de développement plus efficientes. 

Pour faire un parallèle avec la vie courante, la librairie est votre collègue, à qui vous demandez de l'aide en fonction de son expertise et qui va vous répondre en offrant la solution à votre problème. Tandis que le framework, est votre entreprise, qui vous met à disposition un téléphone, une imprimante, un ordinateur, etc. vous permettant de travailler efficacement afin de que vous puissiez produire une solution. Autrement dit, vous dépendez de la librairie (votre collègue) qui va vous donner une partie de la solution, mais ne vous offre aucune commodité particulière pour y parvenir, au contraire du framework (l'entreprise) qui dépend de vous pour trouver la solution, mais qui vous offre une série d'instruments pour y arriver.

>A noter que certains framework et librairies peuvent être payantes.

## Suivants

- [Les outils de suivi de projet](outils/outils-projet.md)
- [Les systèmes et langages informatiques](developpement-dun-projet-it/langages-et-systemes.md)
- [L'architecture d'un système](developpement-dun-projet-it/architecture.md)
