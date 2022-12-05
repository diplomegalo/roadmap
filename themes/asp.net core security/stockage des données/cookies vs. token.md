---
date: 23/11/2022
auteur: Delsaut Pierre-Arnaud
email: diplomegalo@hotmail.com
profils:
 - technique
domaines:
 - securité
themes:
 - cookies
 - token
 - jwt
 - session
tags:
 - cookies
 - token
 - jwt
 - session
 - statefull
 - stateless
 - session storage
 - local storage
 - xss
 - xsrf
 - csrf
references:
 - https://povio.com/blog/handling-authentication-in-spa-with-jwt-and-cookies/
 - https://developer.okta.com/blog/2022/02/08/cookies-vs-tokens
 - https://security.stackexchange.com/questions/225673/is-session-cookie-based-authentication-stateful-or-stateless
versions:
  -
    date: 28/11/2022
    description: 
	  - Ajout des pro et cons
	  - Déplacement du chapitre cookie de session
---

>[!todo]
> - [ ] Cookies vs. tokens
> 	- [ ] Statefull vs. stateless
> 	- [ ] Cookie de session
> 	- [ ] Intégration avec le navigateur
> 	- [ ] Intégration hors navigateur
> 	- [ ] Sécurité
> 	- [ ] Performance et responsabilité
> 	- [ ] Comment choisir

# Cookies vs. *tokens*

Il existe plusieurs différences fondamentales entre l'utilisation de cookies ou de token.

## Statefull vs. stateless

Les cookies sont statefull, tandis que les tokens sont stateless. 

Autrement dit un cookie peut contenir des informations qui peuvent évoluer au fil du temps. Au contraire du JWT qui ne pourra pas être modifié pendant toute la durée de son existence car il est signé sur base de son contenu.

>[!Check] Satefull
>Le cookie peut contenir des données
>

## Intégration avec le navigateur

L'enregistrement des cookies est dans le navigateur est pris en charge par celui-ci par le biai de l'en-tête de la réponse `Set-Cookie`. Il ne faut donc rien développer dans ce cadre au niveau du frontend.

De même, l'association d'un cookie a un *call* est pris en charge automatiquement par le navigateur,  ce qui apporte une garantie en termes de protection contre les attaques de type *cross-site request forgery* (XSRF/CSRF).

En revanche, l'intégration des tokens dans les storage d'un navigateur doit être développé. De la même manière que l'association du token au *call* XHR doit être implémenté dans le code JavaScript.

>[!todo]
> Cons Pros

## Intégration hors navigateur

Si la gestion des cookies est complétement intégré dans le navigateur, ce n'est pas le cas des autres environnements (mobile, desktop, tablets, etc.) qui pourraient avoir besoin des Web API.

Par conséquent, l'utilisation de cookie rends l'utilisation des Web API exclusif aux navigateurs Web.

### Sécurité

S'il est possible de rendre les données d'un cookie irrécupérables par du code JavaScript grâce à la propriété `HttpOnly`, ça ne l'est absolument pas pour un JWT stocké dans le *storage* d'un navigateur. 

Par conséquent, un JWT stocké dans le *storage* du navigateur est sensible au attaque *cross-site scripting*. 

>[!todo]
>Comment protéger le token du XSS

## Performance et responsabilité

Le JWT permet à l'application frontend une plus grande autonomie dans le cadre de l'authentification et évite ainsi de devoir systèmatiquement faire un appel vers le serveur pour savoir si l'utilisateur est authentifié.

Tandis que les cookies vont concentré les logiques dans le serveur, a fortiori dans le cas de Cookie de session

>[!todo]
> Cons Pros

## Comment choisir

La seule contraintes forte est qu'il vous sera impossible d'utiliser les cookies si vos Web API doivent être consomées par d'autres type de client que des navigateurs.

Pour le reste, tout dépendra des besoins, car les deux solutions se valent. 

Généralement les cookies seront utilisé dans le cadre de Web App implémenté en Asp.NET Core MVC, car dans ce cas le client n'a que très peu de responsabilité et tout modification opère un rechargement de page complet. 

Contrairement au SPA, qui vont être beaucoup plus autonome et posséder des logiques dans le frontend. Dans ce cas, l'utilisation de token sera recommandé étant donnée que l'état de l'application reste en local et que seul des requêtes de modifications sont envoyées au serveur.

Autre point, la gestion des cookies session est plus gourmande en termes de performance pour le serveur. Par conséquent, si votre application est destiné à recevoir une grande quantité de requête, la gestion de l'authentification par token sera plus adéquate. 

Finalement, si votre application fait partie d'un grand ensemble de système et qui intègre un certain nombre de tierces parties, la gestion des tokens est plus flexible et sera donc plus adapté que les tokens.

Toutefois, n'oubliez pas que le token est moins protégé que le cookie et que vous devrez éventuellement mettre en place des systèmes de protection tel que le 

>[!todo]
> Cons Pros