---
date: 
auteur: Delsaut Pierre-Arnaud 
email: pa.delsaut@wavenet.be
profils:
domaines:
themes:
tags:
---

Rider permet d'ajouter des dictionnaire de langue. De cette manière, les erreurs de typo ne sont plus mise en evidence. Attention toute fois que les caractères accentués sont pris en compte dans la correction orthographique.

Pour ajouter un dictionnaire français : 
1. Ajouter le [plugin Hunspell](https://plugins.jetbrains.com/plugin/10275-hunspell)
2. Récupérer les sources des dictionnaires. J'ai personnellement repris celle de [JetBrains-Hunspell](https://github.com/JetBrains/hunspell-dictionaries.git), mais il en existe d'autres. Vous trouverez la liste des sources des dictionnaires sur la page du plugin.
3. Ajouter les fichiers du dictionnaire dans Settings > Spellings > Custom dictionaries . En ce qui concerne le dictionnaire français, j'ai repris les fichiers `fr.aff` et `fr.dic`.

## Référence

- https://plugins.jetbrains.com/plugin/10275-hunspell
- https://github.com/wooorm/dictionaries