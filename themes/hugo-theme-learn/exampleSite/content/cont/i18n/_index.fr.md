---
date: 2024-06-17
title: Multi-langue et i18n
weight: 30
---

**Learn** est complÃ¨tement compatible avec le mode multi-langue d'Hugo.

Il fournit :

- Des *translation strings* pour les valeurs par dÃ©faut utilisÃ©es par le thÃ¨me (Anglais et FranÃ§ais). N'hÃ©sitez pas Ã  contribuer !
- GÃ©nÃ©ration automatique du menu avec le contenu multi-langue
- Modification de la langue dans le navigateur

![I18n menu](/en/cont/i18n/images/i18n-menu.gif)

## Configuration simple

AprÃ¨s avoir appris [comment Hugo gÃ¨re les sites multi-langue](https://gohugo.io/content-management/multilingual), dÃ©finissez vos langues dans votre fichier `config.toml`.

Par exemple, pour ce site, avec du contenu en franÃ§ais et en anglais.

```toml
# Anglais est la langue par dÃ©faut
defaultContentLanguage = "en"
# Force d'avoir /en/ma-page et /fr/ma-page routes, mÃªme avec la langue par dÃ©faut.
defaultContentLanguageInSubdir= true

[Languages]
[Languages.en]
title = "Documentation for Hugo Learn Theme"
weight = 1
languageName = "English"

[Languages.fr]
title = "Documentation du thÃ¨me Hugo Learn"
weight = 2
languageName = "FranÃ§ais"
```

Puis, pour chaque nouvelle page, ajoutez *l'id* de la langue du fichier.

- Le fichier `my-page.md` est dÃ©coupÃ© en deux fichiers :
    - en anglais : `my-page.en.md`
    - en franÃ§ais : `my-page.fr.md`
- Le fichier `_index.md` est dÃ©coupÃ© en deux fichiers :
    - en anglais: `_index.en.md`
    - en franÃ§ais: `_index.fr.md`

{{% notice info %}}
Attention, seulement les pages traduites sont affichÃ©es dans le menu. Le contenu n'est pas remplacÃ© par les pages de la langue par dÃ©faut.
{{% /notice %}}

{{% notice tip %}}
Utilisez le paramÃ¨tre du Front Matter [slug](https://gohugo.io/content-management/multilingual/#translate-your-content) pour traduire Ã©galement les URLs.
{{% /notice %}}

## Surcharger les *translation strings*

Les *Translations strings* sont utilisÃ©es comme valeurs par dÃ©faut dans le thÃ¨me (Bouton *Modifier la page*, Element de subsitution *Recherche*, etc.). Les traductions sont disponibles en franÃ§ais et en anglais mais vous pouvez utiliser n'importe quelle autre langue et surcharger avec vos propres valeurs.

Pour surcharger ces valeurs, crÃ©er un nouveau fichier dans votre dossier i18n local `i18n/<idlanguage>.toml` et inspirez vous du thÃ¨me `themes/hugo-theme-learn/i18n/en.toml` 

D'ailleurs, ces traductions pour servir Ã  tout le monde, donc svp prenez le temps de [proposer une Pull Request](https://github.com/matcornic/hugo-theme-learn/pulls) ! 

## DÃ©sactiver le changement de langue

Vous pouvez changer de langue directement dans le navigateur. C'est une super fonctionnalitÃ©, mais vous avez peut-Ãªtre besoin de la dÃ©sactiver. 

Pour ce faire, ajouter le paramÃ¨tre `disableLanguageSwitchingButton=true` dans votre `config.toml`

```toml
[params]
  # Quand vous utilisez un site en multi-langue, dÃ©sactive le bouton de changment de langue.
  disableLanguageSwitchingButton = true
```

![I18n menu](/en/cont/i18n/images/i18n-menu.gif)
