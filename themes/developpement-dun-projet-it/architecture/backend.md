---
profils: [management, technique]
domaines: developpement
themes: backend
tags:
 - API
---
# Application Backend


En retrait des applications _[frontend](frontend.md)_, il existe d'autres types d'applications ou système, nécessaire au bon fonctionnement de l'ensemble d'une solution informatique.


L'exemple le plus simple pour comprendre est celui de l'application mobile qui vous permet de faire vos courses alimentaires en ligne. Seule, cette application mobile ne peut pas contenir tout le catalogue à jour de produits de votre supermarché, car cela prendrait trop de place sur l'appareil mobile. Pourtant, vous devez pouvoir naviguer dans l'application à la recherche d'un produit en particulier. Pour ce faire, l'application mobile utilisera une autre application dite _backend_ pour récupérer les données du catalogue à afficher dans l'application mobile. Cette API (Interface de Programmation Applicative), hébergée sur un serveur Web distant de manière à pouvoir être appelée de n'importe quel endroit, sera donc requêtée par l'application mobile de manière à récupérer la liste des articles à afficher. Elle sera également requêtée pour toutes autres actions, comme la validation du panier d'achats, le paiement, la consultation de l'historique des courses, etc. 


>:blue_book: Une API ou **I**nterface de **P**rogrammation **A**pplicative est une application offrant une liste de services définit au travers d'un protocole. Dans le cas où une application offre des services (ou fonctionnalités) au travers du Web, on parlera naturellement de Web API. Un exemple typique serait une Web API météo, qui permettrait à une application de demander la température actuelle d'une région du monde. 

## Suivants

- [les applications frontend](./architecture/frontend.md) 
- [les applications backend](./architecture/backend.md) 
- [les systèmes de gestion de base de données](./architecture/sgbd.md)
