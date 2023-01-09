---
date: 
auteur: Delsaut Pierre-Arnaud 
email: pa.delsaut@wavenet.be
profils:
domaines:
themes:
tags:
---
# Les outils

Pour construire il faut des outils, certains petits et multi-fonctions comme un marteau pouvant aider dans de nombreuses circonstances, d'autres gigantesques et ultra-spécifique comme une grue de chantier ne servant qu'a une et une seule chose : le transport de charge lourde d'un point à un autre du chantier.

D'autres outils vous permettent également un meilleur suivi, comme le talkie walkie entre le grutier et le chef des opérations.

En outre, certains outils sont fabriqués au fil de la construction, par exemple les échaffaudages qui serviront de structure temporaire et dont l'empleur de la structure varira en fonction de l'état d'avancement du projet.

De la même manière, un projet informatique requiert bon nombre d'outils offrant une aide tant dans la gestion, que le suivi et l'élaboration du livrable.

En règle générale, les outils font partie d'un ensemble d'application gérée par un département informatique et sont installés aupréalable sur les machines destinées aux développeurs. Dans tous les cas, l'équipe de développement est complétement autonome et sera la plus à même de remonter un besoin dans ce cadre.  

## Les outils de développement

L'ensemble des outils requis pour développer sont l'environnement de développement, l'IDE et le gestionnaire de sources. Ensemble, il forme la base nécessaire au développeur construire la solution.

L'environnement de développement, est tout bonnement l'ensemble des appareils et accessoires qui permettront aux techniciens de réaliser le livrable, ça peut aller du clavier à l'ordinateur ou le gsm portable sur lequel le développeur installe et test l'application.

L'IDE qui est un environnement de développement intégré regroupant :

- l'éditeur de code qui permet aux développeurs d'écrire les sources de l'application,
- le compilateur qui permet de construire l'application,
- le débogueur qui permet de parcourrir le code pas à pas lors de l'exécution de l'application de manière à avoir une vue exacte des valeurs circulant à travers le code et le cas échéant de corriger le code en cas de bug ;

Le gestionnaire de source qui permet de centraliser les lignes de codes émanant des différents développeurs, mais également de les fusionner et d'en gérer l'historique des versions de manière à ne pas perdre d'informations accidentellement. En outre, les gestionnaires de source vont offrir des services supplémentaires telle que la maintenance automatique du code mais également des services de déploiement automatiques les environnement de développement, d'acceptance et production (cf. [[les environnements d'exécutions]]).

A cela peuvent s'ajouter d'autres outils particulièrement utiles comme : 
- l'outils de développement du navigateur Web qui permet nottament de 
	- debugger l'exécution du code JavaScript directement depuis le navigateur,
	- de récupérer les informations stocker,
	- de visionner les différents messages et fichier qui ont été échangé avec un serveur ;
- un client Web API nécessaire pour interroger un Web service distant ;
- un client SQL utile pour interroger une base de données.

### Les IDE

Les IDE sont des éditeurs de code. ll permettent aux développeurs de concevoir l'application mais également de la "construire". Par conséquent, ils sont fortement lié à la technologie ou au language de programmation.

Une fois un code éditer, le développeur va passer par plusieurs phase pour vérifier la qualité de son code, comme on pourrait le faire communément avec un vérifieur orthographique. Cette étape s'appelle la compilation. Cette étape a également comme finalité de "construire" un binaire, autrement dit l'application ou le système exécutable. C'est ce binaire qui est ensuite déployé dans [[les environnements d'exécutions]], c'est-à-dire là où s'exécute l'application. Ces binaires peuvent avoir différentes extensions de fichier comme .dll, exe, .war, .jar, etc.

Les IDE les plus connus sont 
- Visual Studio pour tous les languages lié à .NET, 
- Eclipse pour le Java, 
- PHP Storm pour le PHP.  

### Les clients SQL

Les bases de données permettent d'enregistrer, de modifier, de supprimer et de lire des informations. Les applications éditées possèdent un connecteur vers cette base de données et c'est via ce connecteur que s'exécute les opérations sur les données. Les commandes sont écrites en langage SQL (Structured Query Language). 

Le client SQL est un programme qui permet d'accéder à une base de données et d'éditer des requêtes SQL. Ce client va donc permettre d'intéragir directement avec la base de données sans attendre que l'application soit complétement développée et par conséquent préparer les données pour des tests ou vérifier si une opération effectuée depuis l'application a bien produit le résultat attendu en base de données.

### Les clients Web API

Généralement une application fait parti d'un écosystème plus vaste, où d'autres systèmes sont utilisés pour rendre des services comme l'authentification ou l'envoie de mail. Ces services sont accessibles selon des protorocole défini. 

>Un protocole est la définition du moyen de communication entre deux systèms. Un exemple de protocole informatique connu de tous est l'HTTP. Il définie comment une client (navigateur web) va intéroger un service (serveur Web) pour recevoir en retour une page HTML à afficher à l'écran.

Le client HTTP permet de se connecter à un serveur de la même manière qu'un navigateur Web, sauf que dans ce cas, il ne s'attend pas à recevoir que de l'HTML, mais tout les types de retour que le protocol HTTP supporte. Autrement dit, il recoit la donnée brut sans en interpréter le contenu, comme le ferait un navigateur Web en affichant des composants graphiques à l'écran tel que des champs ou des boutons. Ce client permet donc de vérifier que la réponse d'une requête est duement formatée ou complétée et de cette manière écarter la piste d'une problématique quelconque émanant du service. 

>L'HTML est interprété par les navigateurs de manière à pouvoir afficher des éléments sur un écran. Les éléments sont du texte, un champs dans lequel introduire une donnée, un bouton. Outre l'HTML, le navigateur est en mesure d'interpréter d'autres langage comme le CSS, qui permettra d'afficher les éléments dans un format différents, c'est-à-dire une taille, une couleur, ou une police différente. 

Une autre méthode plus imagée pour comprendre à quoi sert le client HTTP serait la mise en oeuvre d'une pièce de théatre. Aupréable des répétitions générales et des représentations en public, les acteurs répêtent en apprenant leur texte seul et en simulant les réponses, par exemple quand l'actrice qui interprête le rôle de Juliette dit : "Oh, mon Roméo !", elle sait en lisant le script que son futur interlocuteur doit lui répond "Oh, ma Juliette !". De la même manière, lors d'un projet, on va d'un coté développer l'application, et de l'autre simuler les appels vers les services extérieurs avec le client HTTP de manière à nous assurer ce qu'ils répondent, pour finalement vérifier que les messages entre les systèmes sont bien cohérents.

## Les outils de suivi de projet

Outre la conception code, il est également utile de suivre l'état d'avancement du projet. D'un point vue strict de gestion de projet, l'objectif est d'avoir une vue de ce qui a été fait, de ce qui est en train d'être fait et de ce qui doit être fait. Tandis qu'un analyste doit être en mesure de concuptualiser les fonctionnalités à implémenter.

A ce titre plusieurs outils seront nécessaires :
- une suite d'application bureautique permettant la rédaction des documents,
- un espace de gestion documentaire pour centraliser les documents,
- un outil applicatif de gestion des tâches. Cet outil peut être spécifique à une méthodologie offrant des fonctionnalités propre à celle-ci.

### Les outils de gestion de tâches

Ces outils offrent généralement une vue centralisée des tâches terminées, à faire ou en cours, de manière à ce rendre compte de l'état d'avancement d'un projet. Ils permettent également de créer et d'organiser les tâches entre-elles. Généralement les outils sont spécifiques à une méthodologie de gestion de projet tel que l'Agile. Par conséquent, les fonctionnalités seront inhérentes à cette méthodologie.

### Les wikis

Les wikis sont des espaces d'édition de documentation simple qui produisent des fichiers markdown. Ils offrent la possibilité de hierarchiser plusieurs page entres-elles comme on pourrait le faire avec des chapitres et des titres. Ils sont utiles pour éditer les informations en rapport avec le projet. Le wiki le plus connu est bien évidemment wikipédia qui a comme ambition d'être une encyclopédie ouverte et éditable par tout le monde. De la même manière, le wiki permet de centraliser et organiser les informations afin que chacun puisse y accéder et les éditer.

### Les outils de gestion documentaire

Les outils de gestion documentaire permettent d'organiser les documents mais également d'indexer leur contenu de manière à pouvoir les trouver facilement via un outil de recherche. Contrairement à un wiki, l'outil de gestion documentaire ou GED, ne va pas permettre d'éditer le contenu des documents.