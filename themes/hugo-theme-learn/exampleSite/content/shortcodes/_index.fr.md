---
date: 2024-06-17
title: Shortcodes
pre: "<b>3. </b>"
weight: 15
---

Hugo utilise Markdown pour son format simple. Cependant, il y a beaucoup de chose que Markdown ne supporte pas bien. On pourrait utiliser du HTML pur pour amÃ©liorer les capacitÃ© du Markdown.

Mais c'est probablement une mauvaise idÃ©e. Tout le monde utilise le Markdown parce que c'est pur et simple Ã  lire mÃªme lorsqu'il est affichÃ© en texte brut. Vous devez Ã©viter le HTML autant que possible pour garder le contenu simple.

Cependant, pour Ã©viter les limitations, Hugo a crÃ©Ã© les [shortcodes](https://gohugo.io/extras/shortcodes/). Un shortcode est un bout de code (*snippet*) dans une page.

**Hugo-theme-learn** fournit de multiple shortcodes en plus de ceux existant.

{{%children style="h2" description="true" %}}
