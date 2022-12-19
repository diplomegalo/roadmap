---
date: 13/12/2022
auteur: Delsaut Pierre-Arnaud
email: pa.delsaut@wavenet.com
profils: 
 - management
domaines:
 - projet
themes:
 - projet
tags:
 - architecture
 - application
 - frontend
 - backend
 - front office
 - back office
references:
---
# Les composants d'une architecture

## Application Frontend

Généralement, les types applications demandés par un client sont :

- une application web utilisée sur un navigateur web,
- une application mobile qui s'exécute sur un téléphone portable,
- une application desktop, appelé également client lourd, qui s'installe et s'exécute sur un ordinateur.

Ces trois types d'applications sont dites *frontend*. Ce terme définit une application qui tourne sur un dispositif informatique exposant une interface graphique utiliser par une personne.

Elles sont subdivisées en deux grandes catégories : les applications *front-office* ou extranet et les applications *backoffice* ou intranet. La différence est fonction de l'utilisateur final et de son besoin. Celles-ci peuvent faire partie d'une seul et même application, ou au contraire être séparées l'une de l'autre de manière à avoir des cycles de développement et de déploiement découplé.

Une application *front office* ou extranet aura pour vocation d'offrir des fonctionnalités à un client qui en aurait besoin. Les fonctionnalités peuvent être d'ordre commercial, comme la vente d'article, ou de services telle que la gestion de mails. Généralement, la portée des fonctionnalités ne concerne que l'utilisateur connecté. Par exemple, lors d'un achat d'article, seul le panier du client est modifié.

Une application *backoffice* ou intranet aura pour fonction de gérer un système ou d'en administrer les informations. Son utilisation est requise par un administrateur, c'est-à-dire une personne clé, définie comme ayant la responsabilité du maintien des données du système. Cette responsabilité va de l'ajout d'une simple information affichée dans le fil d'actualité d'un site web à destination commercial (e-commerce), jusqu'à la mise à jour des quantités de stocks d'un produit ou de données comptables de ce même site. Ces informations sont souvent sensibles et ont une portée qui touche l'ensemble de l'application.

>Un utilisateur dans un projet informatique est communément appelé acteur, il en existe deux types :
>- l'acteur physique qui désigne une personne vivante qui peut interagir avec une interface graphique,
>- l'acteur système qui représente un dispositif informatique ou une machine avec laquelle on communique au travers d'interface applicative de programmation (API).

## Application Backend

En retrait de ces applications *frontend*, il existe d'autres types d'applications ou système, nécessaire au bon fonctionnement de l'application.

L'exemple le plus simple et celui de l'application mobile qui vous permet de faire vos courses alimentaires en ligne. Seule, cette application installée sur un dispositif mobile ne peut contenir tout le catalogue de votre supermarché. Néanmoins, vous devez en disposer de manière à le parcourir lorsque vous naviguez d'un menu à l'autre où lors d'une recherche d'un type de produit en particulier. À ce titre, l'application mobile va utiliser une autre application, qui elle a la responsabilité de lui donner toutes les informations nécessaires en ce qui concerne le catalogue d'article. Cette autre application est hébergée sur un environnement extérieur et disponible au travers de l'internet. L'application mobile pourra dès lors la requêter en fonction des données dont elle a besoin pour les afficher à l'écran.

Ces applications sont dites *backend* et sont de manière générale des API, c'est-à-dire des Interface de Programmation Applicative. On les trouve communément sous les formes décrites ci-dessous où chacune emploie un protocole, c'est-à-dire un moyen de communiquer, différent.

- Les services web exposant des fonctionnalités appelables via l'internet.
- Les services (Windows) ou deamon (Linux) qui sont des applications hébergées sur un serveur,
- Les applications exécutables

Certaines parties développées lors d'un projet IT peuvent n'avoir aucun sens fonctionnel. Il s'agit dès lors de briques applicatives considérées comme des outils (cf. [[Les outils applicatifs de développement]]) participant à l'élaboration de l'application finale.

>[!todo]
>- [ ] API
>	- [ ] REST API
>	- [ ] SOAP API
>- [ ] DB
>- [ ] L'ESB
>- [ ] CRM
>	- [ ] Umbraco
>- [ ] ECM
>	- [ ] GED
>	- [ ] Alfresco
>	- [ ] Sharepoint
>- [ ] CMS
>	- [ ] Umbraco
>- [ ] SSO
>	- [ ] AD
>	- [ ] SAML
>- [ ] LDAP


