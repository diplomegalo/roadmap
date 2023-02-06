---
profils: Management
domaines: Projet
themes: Projet
---

# Les outils de développement

## Les outils applicatifs et système

L'ensemble des outils applicatifs requis pour développer une solution informatique sont l'environnement de développement, l'IDE et le gestionnaire de sources. Ensemble, il forme la base nécessaire au développeur construire la solution.

L'environnement de développement, est tout bonnement l'ensemble des appareils et accessoires qui permettront aux techniciens de réaliser le livrable, ça peut aller du clavier à l'ordinateur en passant par le gsm portable sur lequel le développeur installe et test une application mobile. On y retrouve également les systèmes et applications nécessaires, comme pourrait l'être le système d'exploitation (Windows, Linux, Androïd, OSX, etc.).

L'IDE qui est un outil de développement intégré regroupant :

- l'éditeur de code qui permet aux développeurs d'écrire les sources de l'application,
- le compilateur qui permet de vérifier la syntaxe de ce qui est écrit et de construire l'application,
- le débogueur qui permet de parcourrir le code pas à pas lors de l'exécution de l'application de manière à avoir une vue exacte des valeurs circulant à travers celui-ci et le cas échéant de le corriger en cas de bug ;

Le gestionnaire de source qui permet de centraliser les lignes de codes produites par les développeurs, mais également de les fusionner et d'en gérer l'historique de versions. En outre, les gestionnaires de source vont offrir des services supplémentaires telle que la maintenance automatique du code, le déploiement automatiques des applications (cf. **les environnements d'exécutions**).

A cela peuvent s'ajouter d'autres outils particulièrement utiles comme : 
- l'outils de développement du navigateur Web qui permet notament de 
	- debugger l'exécution du code JavaScript directement depuis le navigateur,
	- de récupérer les informations stocker en local de la machine,
	- de visionner les différents messages et fichier qui ont été échangé avec un serveur ;
- un client Web API nécessaire pour interroger un service Web distant ;
- un client SQL utile pour interroger une base de données.

### Les IDE

Les IDE sont des éditeurs de code. ll permettent aux développeurs de concevoir l'application mais également de la "construire". Par conséquent, ils sont fortement lié à la technologie ou au language de programmation.

Une fois le code édité, le développeur va passer par une phase de vérification de celui-ci, comme on pourrait le faire communément avec un vérifieur orthographique. Il s'agit de la compilation. Cette étape a comme finalité de "construire" un binaire, autrement dit l'application ou le système. Ce binaire exécutable est ensuite déployé dans **les environnements d'exécutions**, c'est-à-dire là où s'exécute l'application. Ces binaires peuvent avoir différentes extensions de fichier comme .dll, .exe, .war, .jar, etc.

Les IDE les plus connus sont 
- Visual Studio pour tous les languages lié à .NET, 
- Eclipse pour le Java, 
- PHP Storm pour le PHP.  

### Les clients SQL

Les bases de données permettent, entre autres, d'enregistrer, de modifier, de supprimer et de lire des données. Les applications possèdent un connecteur pour accèder aux bases de données par lesquels ils envoient des commandes de traitement des données appelées _Query_. Les requêtes de traitement ou de récupération de données sont écrites en langage SQL (Structured Query Language). 

Le client SQL est un programme qui permet d'accéder à des bases de données et d'éditer des requêtes SQL. Ce client va donc permettre d'intéragir directement avec la base de données sans attendre que l'application soit complétement développée. De cette manière, il sera possible de récupérer ou préparer des données, par exemple dans le cadre d'exécution de tests.

### Les clients Web API

Généralement une application fait parti d'un écosystème plus vaste où d'autres systèmes, appelés services, sont utilisés. De manière plus générale ces services sont des API, fournissant au travers d'une interface, une multitude de fonctionnalités. Pour requêter cette interface, il faut respecter le protocole qui y est associé, par exemple dans le cadre des Web services, il faut respecter les principes du protocole HTTP.

>Un protocole est la définition du moyen de communication entre deux systèms. Un exemple de protocole informatique connu de tous est l'HTTP. Il définie comment une client va intéroger un serveur Web et comment celui-ci va lui répondre. Ceci va de paire avec la notion de language et d'interaction social qui définit que lorsque l'on pose une question à une personne étrangère, on le salue dans un premier temps, on se présente ensuite, puis seulement on lui demande s'il est disponible et en fonction de sa réponse, on lui pose sa question.

Le client Web API permet de se connecter à un serveur de la même manière qu'une application le ferait afin de recevoir la réponse brut, sans en interpréter le contenu et par conséquent de la vérifier que ce soit en termes de format ou de données. Ce type de client est très utile dans le cadre de tests, car avant même d'avoir implémenté l'application, le développeur est en mesure de créer de requête et d'en analyser le résultat concret, lui permettant ainsi d'appréhender l'implémentation qu'il devra réaliser pour traiter les réponses d'une requête HTTP.  

>L'HTML est interprété par les navigateurs de manière à pouvoir afficher des éléments sur un écran. Les éléments sont du texte, un champs dans lequel introduire une donnée, un bouton, etc. Outre l'HTML, le navigateur est en mesure d'interpréter d'autres langage comme le CSS, qui permettra d'afficher les éléments dans un format différents, c'est-à-dire une taille, une couleur, ou une police différente.

## Les framework et les librairies

Généralement confondu ces deux termes definissent des concepts d'outils différents. Les librairies sont des bibliothéques, une sorte de boite à outils réutilisable en fonction du besoin. Tandis que les framework sont des structures de base qui vont permettre de vous faciliter la tâche en vous offrant des solutions de développement plus efficiente. 

Pour faire un parallèle avec la vie courante, la librairie est votre collègue à qui vous demander de l'aide en fonction de son expertise et qui vous répond en vous offrant la solution, tandis que le framework est votre entreprise qui vous met à disposition un téléphone, une imprimante, un ordinateur, etc. vous permettant de travailler efficacement, mais qui dépend de **votre** travail pour produire une solution. Autrement dit, vous dépendez de la librairie (de votre collègue) qui vous donne une partie de la solution mais ne vous offre aucune commodité particulière, au contraire du framework (l'entreprise) qui dépend de vous pour trouver la solution mais qui vous offre une série d'instrument pour y arriver.

Un exemple concret du monde informatique est le framework de Microsoft appelé  qui permet de développer des applications dans plusieurs languages
