---
date: 28/11/2022
auteur: Delsaut Pierre-Arnaud
email: diplomegalo@hotmail.com
profils:
 - technique
domaines:
 - securité
themes:
 - cookies
 - authentification
tags:
 - cookies
 - authentification
---
# Utilisation d'un cookie d'authentification

Les cookies sont essentiellement utilisés dans le cadre de Web App, où toute l'application est stocké sur le serveur. 

Dans ce cas, le serveur génère une page et l'envoie vers le navigateur auquel il associe le cookie. 

Le client va ensuite renvoyer une requête pour l'affichage d'une autre page auquel il associe le cookie reçu. 

Finalement, le serveur reçoit le requête, valide le cookie associé, génère la nouvelle page et la renvoie vers le navigateur. Si le cookie reçu par le serveur est expiré ou corrompu, le serveur le génère une la page d'authentification et la renvoi vers le navigateur.

```mermaid
sequenceDiagram;
Navigateur->>Server: Requête l'url page.com
Server-->>Navigateur: Renvoi une page avec un formulaire d'authentification
Navigateur->>Server: Envoi le login / mdp 
Server->>Server: Valide les données de login
note left of Server: Set-Cookie: <nom-du-cookie>=<valeur-du-cookie>
Server-->>Navigateur: Retourne la page page.com avec le cookie
Navigateur->>Server: Requête l'url page.com/news
Server->>Server: Valide le cookie
Server-->>Navigateur: Retourne la page de l'url page.com/news avec le cookie
```

## Ajouter une des données de session