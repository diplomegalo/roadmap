---
date: 18/11/2022
auteur: Delsaut Pierre-Arnaud
email: pa.delsaut@wavenet.be
profil: technique
domaine:
  - securite
  - .net
theme:
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
  - https://learn.microsoft.com/en-us/aspnet/core/security/?view=aspnetcore-7.0
  - https://www.softwaretestinghelp.com/cross-site-scripting-xss-attack-test/
  - https://owasp.org/www-community/attacks/xss/
---

# Sécuriser une application ASP.NET Core

## Authentification vs identification vs autorisation 

L'authentification est le processus qui permet au système de déterminer qui vous êtes. Généralement le système demande des informations confidentielles à l'utilisateur, comme son login et son mot de passe et sur base de ces données, le système déterminera s'il est en mesure de vous reconnaitre et par conséquent de vous authentifier. 

Dans le cadre de l'authentification, il faut également prendre en compte l'identification. Il existe deux niveau d'identification : un fort et un faible. 

L'identification permet de savoir si vous êtes bien la personne que vous prétendez être. Les méthodes d'identification garantissent que les données envoyé par l'utilisateur sont bien les siennes. Cette technique se révèle intéressante quand par exemple sur base de votre identifiant nationnal (NISS), un système vous renvoie des données médicale confidentiel. Ce type d'application ne peut pas se permettre de vous laisser remplir ce type de données vous même de manière déclarative, car rien ne vous empêche de rentrer des données usurpés et par conséquent de récupérer des données d'une autre personnes. Généralement dans ce cas une partie tier rentre dans le processus pour garantir l'identité de la personne, par exemple la carte d'identité et l'application de lecture de celle-ci. 

L'autorisation permet au système, sur base de l'authentification, de savoir si l'utilisateur êtes autorisé ou non à utiliser une fonctionnalité d'un système ou à accéder à une ressource.

## Les normes de sécurités

## Les techniques de sécurisation d'un application

### Les cookies

### Les tokens

## Les failles de sécurités

### Cross-site Scripting (XSS) attack

### SQL Injection

### Cross-Site Request Forgery (XSRF/CSRF) attacks

### Open redirect attacks