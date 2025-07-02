---
date: 2024-06-17
title: Tags
weight: 40
tags: ["documentation", "tutorial"]
---


Le *thÃ¨me Learn* supporte une des taxonomy par dÃ©faut de GoHugo : les tags.

## Configuration 

Il suffit d'ajouter un tableau de tags sur la page  : 

```markdown
---
date: 2024-06-17
title: Tutoriel pour le thÃ¨me
weight: 15
tags: ["tutoriel", "theme"] 
---
```

## Comportement

Les tags sont affichÃ©s en haut de la page, dans l'ordre dans lequel ils ont Ã©tÃ© saisis. 

Chaque tag est un lien vers une page *Taxonomy*, qui affiche tous les article avec ce tag.


## Liste des tags

Il est possible de rajouter un raccourci dans le fichier `config.toml` afin d'afficher une page listant tous les tags

```toml
[[menu.shortcuts]]
name = "<i class='fas fa-tags'></i> Tags"
url = "/tags"
weight = 30
```
