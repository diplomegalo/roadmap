---
date: 18/11/2022
auteur: Delsaut Pierre-Arnaud
email: pa.delsaut@wavenet.be
profils: technique
domaines:
  - securite
  - .net
themes:
  - asp.net core
  - securite
  - authentification
  - autorization
  - identity
tags:
  - asp.net core
  - securite
  - authentification
  - autorization
  - jwt
  - cookie
  - xss attack
  - sql injection
  - XSRF/CSRF attacks
  - open redirect attacks
references:
  - https://learn.microsoft.com/en-us/aspnet/core/security/
  - https://www.softwaretestinghelp.com/cross-site-scripting-xss-attack-test/
  - https://owasp.org/www-community/attacks/xss/
  - https://developer.mozilla.org/en-US/docs/Glossary/MitM
  - https://developer.okta.com/blog/2022/02/08/cookies-vs-tokens
---

>[!todo]
> - [x] Sécuriser une application ASP.NET Core
> 	- [x] Authentification, identification, autorisation
> - [ ] Echanger les données d'authentification
> 	- [x] Les cookies
> 	- [ ] Les tokens
> 	- [ ] OAuth 2.0
> 	- [ ] OpenID Connect
> 	- [ ] Https
> 	- [ ] Les failles de sécurités
> 		- [ ] Cross-site Scripting (XSS) attack
> 		- [ ] Sql Injection
> 		- [ ] Cross-Site Request Forgery attacks
> 		- [ ] Open redirect attacks
> 		- [ ] Man in the middle

# Coup d'oeil sur les principes de sécurité d'une application Web

## Les concepts de la sécurité

Sécuriser une application repose sur deux fonctionnalités, l'authentification et l'autorisation. L'authentification peut être étendu par la notion d'identification qui ajoute une contrainte de sécurité supplémentaire pour garantir l'identité de l'utilisateur.

### Authentification

L'authentification est le processus qui permet au système de déterminer qui vous êtes. Généralement le système demande des informations confidentielles à l'utilisateur, comme son login et son mot de passe et sur base de ces données, le système déterminera s'il est en mesure de vous reconnaitre et par conséquent de vous authentifier. 

### Identification

Dans le cadre de l'authentification, il peut être nécessaire de garantir l'identité de l'utilisateur. 

L'identification permet de savoir si vous êtes bien la personne que vous prétendez être. Les méthodes d'identification garantissent que les données envoyé par l'utilisateur sont bien les siennes. Cette technique se révèle intéressante quand par exemple sur base de votre identifiant nationnal (NISS), un système vous renvoie des données médicales confidentiels. Ce type d'application ne peut pas se permettre de vous laisser vous enregistrer de manière déclarative, en remplissant un formulaire d'inscription par exemple, car rien ne vous empêche d'introduire des données d'identification usurpés et par conséquent de récupérer des données d'une autre personnes en se faisant passer pour elle. Généralement dans ce cas une partie tier rentre dans le processus pour garantir l'identité de la personne, par exemple la carte d'identité et l'application de lecture de celle-ci. 

### Autorisation

L'autorisation permet au système, sur base de l'authentification, de savoir si l'utilisateur est autorisé ou non à utiliser une fonctionnalité d'un système ou à accéder à une ressource. L'autorisation est généralement associé au concepts de rôle ou de groupe.

## Les types d'attaque

### Cross-site Scripting (XSS) attack

### SQL Injection

### Cross-Site Request Forgery (XSRF/CSRF) attacks

### Open redirect attacks

### Man in the middle

## Les processus d'authentification

### Basic Authentication

### OAuth 2.0

### OpenID Connect

### HTTPS

## Stockage des données

L'`http` est par principe stateless. Par conséquent, une fois la réponse à la requête d'authentification reçu, le serveur "oublie" que l'utilisateur est authentifié. 

Par conséquent, pour qu'un utilisateur puisse être faire usage d'une application Web qui tourne sur un navigateur (*user-agent*) et requêter le serveur de manière authentifié, il faut enregistrer les informations d'authentification localement dans le navigateur de manière à les renvoyer systèmatiquement à chaque requête vers le serveur, jusqu'a expiration. 

Pour ce faire, les navigateurs offrent des mécanismes tels que les cookies, ou encore les API du *local storage* et du *session storage*.

### Les cookies

Les cookies sont envoyées par le serveur avec les données d'authentifications pour être stockées sur le navigateur. 

Lors d'une requête d'authentification vers le serveur, celui-ci renvoie une réponse dans lequel il *set* un cookie contenant les données d'authentification. Le navigateur client va alors enregistrer ce cookie et le renvoyer systèmatiquement lors des *call* vers le serveur. De cette manière le serveur sera en mesure de récupérer et valider le cookie de manière à authentifier l'utilisateur.

Voir plus concernant [[Le cookie d'authentification]].

### Les *tokens*