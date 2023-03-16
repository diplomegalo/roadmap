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
- https://mrcoles.com/blog/cookies-max-age-vs-expires/
- https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Set-Cookie
- https://www.rfc-editor.org/rfc/rfc6265
- https://learn.microsoft.com/en-us/aspnet/core/fundamentals/app-state?view=aspnetcore-7.0
versions:
  -
    date: 28/11/2022
    description: 
      - Correction syntaxique et validation des chapitres
      - Déplacement du chapitre cookie d'authentification
      - Suppression d'un cookie
---

>[!todo]
> - [ ] Vérification orthographique
> - [ ] Les cookies
> 	- [x] Les propriétés
> 		- [x] `Max-Age` et `Expires`
> 		- [x] Domain
> 		- [x] Secure
> 		- [x] HttpOnly
> 		- [x] SameSite
> 	- [ ] Cookie de session
> 		- [ ] Gestion de la session
> 	- [x] Cookie permanent
> 	- [x] Création d'un cookie

# Les cookies

Un cookie est un ensemble d'information échangé entre un client et un navigateur. Généralement le cookie est créé par le serveur pour garder des informations d'états, comme par exemple une session, un caddie, des préférences utilisateurs. Dès lors qu'un navigateur reçoit un cookie du serveur, il le stocke localement. Le navigateur (*user-agent*), selon les paramêtres du cookie, est en mesure d'extraire les informations du cookie et le cas échéant les modifier (cf. [HttpOnly](#HttpOnly)). 

Une fois le cookie enregistré, le navigateur l'associe automatiquement à toutes les requêtes. C'est pour cette raison qu'il faut limiter au maximum la taille du cookie. Certains navigateurs vont limiter eux-même la taille du cookie et le refuser le cas échéant.

Les cookies peuvent être facilement falsifiable, par conséquent il est nécessaire de pouvoir les valider.

>[!note]
>Le client peut lui aussi créer un cookie mais ce point ne sera pas étudier ici.

## Les propriétés 

Les informations d'un cookie sont :

| clé                            | valeur                                                                             |
| ------------------------------ | ---------------------------------------------------------------------------------- |
| `<cookie-name>=<cookie-value>` | La nom et l'informations du cookie                                    |
| `Expires=<number>`             | Le nombre de secondes après lesquelles le cookie sera supprimé                     |
| `Max-Age=<date>`               | La date d'expiration du cookie après laquelle le cookie doit être supprimé         |
| `Domain=<string>`              | Définie l'*host* du cookie.                                |
| `Path=<string>`                | Définie l'`URI` du cookie.                                |
| `Secure`                       | Permet de spécifier que le cookie ne peut être envoyé qu'avec une requête `https`. |
| `HttpOnly`                     | Permet de déterminer si les données du cookie sont accessible en JavaScript.       |
| `SameSite=<samesite-value>`    | Permet de définir l'autorisation de requêtes `cross-site`.                                                                                   |

Les propriétés d'un cookie vont avoir une incidence, en termes de sécurité, 
- sur la durée d'une session d'utilisation avant expiration, 
- sur la sécurité et l'intégrité des données d'authentifications contenu dans le cookie,
- sur les requêtes auquelles seront associés le cookie sur base du domaine et du chemin de l'`URL`, autrement dit le serveur qui reçoit les données du cookie.

### `Max-Age` et `Expires`

Les propriétés `Max-Age` et `Expires` ont la même conséquence : l'expiration et par conséquent la suppression du cookie. Néanmoins le type de valeur des propriétés est différent.

`Max-Age` contient une valeur de type `number` correspondant au nombre de seconde jusqu'auquelle le cookie expire. Une valeur `0` ou négative signifie que le cookie expire immédiatement.

`Expires` contient une valeur de type `date` correspondant à la date à laquelle le cookie expire et par conséquent est supprimé. S'il n'y a pas de valeur défini, alors le cookie devient un cookie de session.

Si les deux propriétés sont présentes, seule la valeur de `Max-Age` est pris en compte par le navigateur.

### Domain

Cette valeur permet de définir le domaine associé au cookie. Par défaut la valeur est celle du domaine de l'URL courante.

Des domaines multiples, ne sont pas possible, mais dans le cas où un domaine est spécifié **explicitement** les sous domaines automatiquement sont inclus.

Cette valeur est utile dans le cadre des comportements d'envoie du cookie sur base de la valeur [[#SameSite]].

Le cookie sera rejeté par le navigateur si le domaine du serveur qui envoie la réponse avec l'en-tête `Set-Cookie` vers le navigateur, est différent de la valeur contenu dans la propriété domaine du cookie. Par exemple, si le serveur a comme domaine :

```
original-domaine.com
```

et que l'en-tête a comme valeur :

```
Set-Cookie: plip=plop; domain=other-domaine.com
```

De même, le cookie sera rejeté si le valeur du domaine est défini pour un sous domaine. Par exemple, si le domaine du serveur est : 

```
foo.com
```

et que l'en-tête a comme valeur :

```
Set-Cookie: plip=plop; domain=sub.foo.com
```

### Secure

Cette valeur permet de s'assurer que le cookie ne sera transmis uniquement que via le protocol `https`, ce qui garantit l'encryptage des données et une meilleur protection contre les attaques de type *Man in the middle*. 

### HttpOnly

Permet de garantir que le client n'est pas en mesure de lire ou modifier les données contenu dans le cookie via du code JavaScript (`document.cookie`) et par conséquent garantit l'intégrité des données.

A noter que même si le JavaScript ne sait pas lire les données du cookie, les méthodes de requêtes *XHR* associent quand même le cookie à la requête, ce qui atténue les problèmatiques de *cross site scripting* (XSS).

### SameSite

Permet de gérer la transmission du cookie lors de requêtes `cross-site`, autrement dit l'envoie du cookie entre deux serveurs de domaines différents. Cette propriété apporte une protection contre les *cross-site request forgery attacks* (CSRF). Ci-dessous la liste exhaustive des valeurs. 

`Strict` défini que le cookie n'est envoyé que si l'origine et la destination de la requête ont le même domaine et le même protocol que celui définit dans le cookie. Par conséquent, les requêtes ne seront autorisées que **vers** le **même domaine** du cookie, et **depuis** le **même domaine** du cookie.

`Lax` défini que le cookie n'est pas envoyé lors de requêtes *cross-site*, mais qu'il le sera lors de requête vers le domaine définie dans le cookie et cela même depuis un site externe dont l'origine est différente du domaine du cookie. Par conséquent, les requêtes ne seront autorisées que **vers** le **même domaine** du cookie, mais **depuis n'importe quel domaine**.

`None` défini que le navigateur envoi les cookies que ce soit lors de requêtes *cross-site* ou *same-site*. Par conséquent, les requêtes sont autorisées **vers n'importe quel domaine**, **depuis n'importe quel domaine**. La propriété `Secure` doit être présente lorsque `None` est utilisé : `SameSite=None; Secure`.

## Cookie de session

Un cookie de session ne contient pas d'information d'expiration. Dès lors, le cookie est supprimé à la fermeture du navigateur. 

>[!warning] Restauration
>Certains navigateurs possèdent une fonctionnalité de restauration de session. Dans ce cas, tous les onglets seront restaurés ainsi que les cookies, comme si le navigateur n'avait jamais été fermé.

### Gestion de la session

Généralement, le client reçoit un identifiant de session et le serveur gardent en mémoire (cache) l'état de cette session. De cette manière, lorsque l'utilisateur modifie l'état de sa session, par exemple en ajoutant un article dans son panier, le serveur reçoit la requête, modifie la session sur base de l'identifiant et renvoie la page avec les données raffraichi.

Il est déconseillé d'utilisé la session pour garder des informations sensibles. En outre, elle présente des désavantages dans le cas d'architecture multi-serveur avec load balancer car il existe un lien fort entre le client et le serveur. En effet, dans le cas où les serveurs sont placés derrière un *load balancer*, il faut garantir une *sticky session* durant tout la session, c'est-à-dire, garantir que ce sera toujours le même serveur qui répondra au requêtes. Une solution à ce problème est de stocker la session, non pas dans une cache, mais en base de donnée avec le désavantage d'une gestion plus lourde et d'une performance plus couteuse. 

De même, l'utilisation de session n'est pas possible avec l'utilisation de SignalR.

## Cookie permanent

Un cookie permanent contient une donnée d'expiration qui, sur base de cette date, permet de supprimer le cookie.

## Création d'un cookie

Pour créer un cookie dans le navigateur, le serveur doit ajouter dans l'en-tête de la réponse `Set-Cookie` suivi des données du cookie.

```
Set-Cookie: <name>=<value>[; <Max-Age>=<number>] [; Expires=<date>][; Domain=<domain-value>] [; Path=<path-value>][; Secure][; HttpOnly]
```

Pour ajouter plusieurs cookie, il faut répéter l'en-tête `Set-Cookie` autant de fois que nécessaire. Attention néanmoins que certains navigateurs limite le nombre de cookie.

## Suppression d'un cookie

Il est impossible de supprimer un cookie. Pour ce faire il faut remplacer la date de d'expiration par une date antérieure à la date actuelle. 

---
Voir aussi : 
- [[cookies vs. token]]
- [[créer un cookie de session sécurisé en .net core]]
