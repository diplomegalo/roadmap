# Les composants d'une architecture

## Application Frontend

Généralement, les types applications demandées par un client sont :

- une application web utilisé via un navigateur Web, 
- une application mobile qui s'exécute sur un téléphone portable,
- une application desktop, appelé également client lourd, qui s'installe et s'exécute sur un ordinateur.

Ces trois types d'applications sont dites *frontend*. Ce terme définie une application qui tourne sur un dispositif informatique exposant une interface graphique destiné à être manipulé par une personne physique : l'utilisateur final. 

Elles sont subdivisées en deux grandes catégories : les applications *front-office* ou extranet et les applications *backoffice* ou intranet. La différence est fonction de l'utilisateur finale et de son besoin. Celles-ci peuvent faire partie d'une seul et même application, ou au contraire être séparé l'une de l'autre de manière à avoir des cycles de développement et de déploiement découplé.

Une application *frontoffice* ou extranet aura pour vocation d'offrir des fonctionnalités à un client qui en aurait besoin. Les fonctionnalités peuvent être d'ordre commercial, comme la vente d'article, ou de services tel que la gestion de mails. Généralement la porté des fonctionnalités ne concerne que l'utilisateur connecté. Par exemple, lors d'un achat d'article, seul le panier du client est modifié.

Une application *backoffice* ou intranet aura pour fonction de gérer un système ou d'en administrer les informations. Son utilisation est requise par un adminstrateur, c'est-à-dire une personne clé, définie comme ayant la responsabilité du maintien des données du système. Cette responsabilité va de l'ajout d'une simple information affichées dans le fil d'actualité d'un site web à destination commercial (e-commerce), jusqu'à la mise à jour des quantité de stocks d'un produit ou de données comptables de ce même site. Ces informations sont souvent sensibles et ont une portée qui touche l'ensemble de l'application.

>Un utilisateur dans un projet informatique est communément appelé acteur, il en existe deux types : 
>- l'acteur physique qui désigne une personne vivante qui peut intéragir avec une interface graphique,
>- l'acteur système qui represente un dispositif informatique ou une machine avec laquelle on communique au travers d'interface applicative de programmation (API).

## Application Backend

En retrait de ces applications *frontend*, il existe d'autres types d'applications ou système, nécessaire au bon fonctionnement de l'application. 

L'exemple le simple et celui de l'application mobile qui vous permet de faire vos courses alimentaire en ligne. Seule, cette application installée sur un dispositif mobile ne peut contenir tout le catalogue de votre supermarché. Néanmoins vous devez être en mesure de le parcourir lorsque vous naviguez d'un menu à l'autre où lors d'une recherche d'un type de produit en particulier. A ce titre, l'application mobile va utiliser une autre application qui elle à la responsabilité de lui donner toutes les informations nécessaires en ce qui concerne le catalogue d'article. Cette autre application est hébergée sur un environnement extérieur et disponible au travers de l'internet. L'application mobile pourra dés lors la requêter en fonction des données dont elle a besoin pour les afficher à l'écran.

Ces applications sont dite *backend* et sont de manière générale des API, c'est-à-dire des Interface de Programmation Applicative. On les trouve communément sous les formes décritent ci-dessous où chacune emploi un protocol, c'est-à-dire un moyen de communiquer, différent. 

- Les services web exposant des fonctionnalités appelable via l'internet.
- Les services (windows) ou deamon (linux) qui sont des applications hébergées sur un serveur,
- Les applications executable

Certaines parties développée lors d'un projet IT peuvent n'avoir aucun sens fonctionnel. Il s'agit dès lors de briques applicative considérées comme des outils (cf. [[Les outils applicatifs de développement]]) participant à l'élaboration de l'application finale.