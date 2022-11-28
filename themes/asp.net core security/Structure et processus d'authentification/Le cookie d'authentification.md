---
date: 23/11/2022
auteur: Delsaut Pierre-Arnaud
email: pa.delsaut@wavenet.be
profils:
  - technique
domaines:
  - securité
themes:
  - cookies
tags: 
  - cookies
  - web app
  - authentification
references:
- https://developer.mozilla.org/fr/docs/Web/HTTP/Cookies
- https://blog.dareboost.com/fr/2016/12/securisez-cookies-instructions-secure-httponly/
---

>[!todo]
> - [x] Description
> - [ ] Les propriétés
> - [ ] Utilisation d'un cookie
> 	- [ ] Limite du cookie (vs. token)

# Description

Un cookie est un ensemble d'information échangé entre un client et un navigateur. Généralement le cookie est créé par le serveur pour garder des informations d'états, comme par exemple une session, un caddie, des préférences utilisateurs. Dès lors qu'un navigateur reçoit un cookie du serveur, il le stocke localement de manière à pouvoir en extraire les informations et le cas échéant les modifier. Le navigateur, lorsqu'il emet une requête vers le serveur, associe automatiquement le cookie à celle-ci. 

A noter que le client peut lui aussi créer un cookie mais ce point ne sera pas pris étudier dans ce chapitre.

## Les propriétés 

Les propriétés d'un cookie sont 
- La clé qui correspond au nom du cookie
- La valeur qui correspond aux informations contenue par le cookie
- La date d'expiration du cookie, autrement dit à quelle date le cookie est-il considéré comme invalide.
- Le flag `HttpOnly` qui permet de déterminer si le navigateur peut avoir accès ou pas au cookie.

```

```

### HttpOnly

De manière à ne pas exploiter les données du cookie du navigateur et de ne pas pouvoir les corrompre, le cookie est :
- Crypté
- Inex

## Utilisation d'un cookie

Les cookies sont essentiellement utilisés dans le cadre de Web App, où toute l'application est stocké sur le serveur. Dans ce cas, le serveur génère une page et l'envoie vers le client auquel il associe le cookie. Le client va ensuite renvoyer une requête pour l'affichage d'une autre page auquel il associe le cookie reçu. Finalement, le serveur recoit le requête, valide le cookie associé, génère la nouvelle page et la renvoie vers le navigateur. Si le cookie reçu par le serveur est expiré ou corrompu, le serveur génère une page d'authentification et le renvoie vers le navigateur.

```mermaid
sequenceDiagram;
Client->>Server: Requête l'url page.com
Server-->>Client: Renvoi une page avec un formulaire d'authentification
Client->>Server: Envoi le login / mdp 
Server->>Server: Valide les données de login
note left of Server: Set-Cookie: <nom-du-cookie>=<valeur-du-cookie>
Server-->>Client: Retourne la page page.com avec le cookie
Client->>Server: Requête l'url page.com/news
Server->>Server: Valide le cookie
Server-->>Client: Retourne la page de l'url page.com/news avec le cookie
```

### Les contraintes d'un cookie