---
date: 2024-06-17
title: Configuration
weight: 20
---

## ParamÃ¨tres globaux du site

En plus de la [configuration globale d'Hugo](https://gohugo.io/overview/configuration/), **Hugo-theme-learn** vous permet de dÃ©finir les paramÃ¨tres suivant dans votre fichier `config.toml` (ci-dessous sont affichÃ©es les valeurs par dÃ©faut).

Notez que certains de ces paramÃ¨tres sont expliquÃ©s en dÃ©tails dans d'autres sections de cette documentation.

```toml
[params]
  # L'URL prÃ©fixe pour Ã©diter la page courante. Ce paramÃ¨tre affichera un bouton "Modifier cette page" on haut de de chacune des pages.
  # Pratique pour donner les possibilitÃ© Ã  vos utilisateurs de crÃ©er une merge request pour votre doc.
  # Allez voir le fichier config.toml de cette documentation pour avoir un exemple.
  editURL = ""
  # Autheur du site, est utilisÃ© dans les informations meta
  author = ""
  # Description du site, est utilisÃ© dans les informations meta
  description = ""
  # Affiche une icÃ´ne lorsque la page a Ã©tÃ© visitÃ©e
  showVisitedLinks = false
  # DÃ©sactive la fonction de recherche. Une valeur Ã  true cache la barre de recherche.
  disableSearch = false
  # Par dÃ©faut, le cache Javascript et CSS est automatiquement vidÃ© lorsqu'une nouvelle version du site est gÃ©nÃ©rÃ©e.
  # Utilisez ce paramÃ¨tre lorsque vous voulez dÃ©sactiver ce comportement (c'est parfois incompatible avec certains proxys)
  disableAssetsBusting = false
  # Utilisez ce paramÃ¨tre pour dÃ©sactiver le bouton copy-to-clipboard pour le code formattÃ© sur une ligne.
  disableInlineCopyToClipBoard = false
  # Un titre est dÃ©fini par dÃ©faut lorsque vous utilisez un raccourci dans le menu. Utilisez ce paramÃ¨tre pour le cacher.
  disableShortcutsTitle = false
  # Quand vous utilisez un site multi-langue, utilisez ce paramÃ¨tre pour dÃ©sactiver le bouton de changement de langue.
  disableLanguageSwitchingButton = false
  # Ordonne les sections dans menu par poids ("weight") ou titre ("title"). DÃ©faut Ã  "weight"
  ordersectionsby = "weight"
  # Utilisez ce paramÃ¨tre pour modifier le schÃ©ma de couleur du site. Les valeurs par dÃ©faut sont "red", "blue", "green".
  themeVariant = ""
  # Fournissez une liste de fichiers css personnalisÃ©s Ã  charger par rapport depuis le dossier `static/` Ã  la racine du site.
  custom_css = ["css/foo.css", "css/bar.css"]
```

## Activer la recherche {#activer-recherche}

Si ce n'est pas dÃ©jÃ  prÃ©sent, ajoutez les lignes suivantes dans le fichier `config.toml`.

```toml
[outputs]
home = [ "HTML", "RSS", "JSON"]
```

Le thÃ¨me *Learn* utilise les derniÃ¨res amÃ©liorations d'Hugo pour gÃ©nÃ©rer un fichier d'index JSON, prÃªt Ã  Ãªtre consommÃ© par le moteur de recherche lunr.js.

> Hugo gÃ©nÃ¨re lunrjs index.json Ã  la racine du dossier `public`.
> Quand vous gÃ©nÃ©rez le site avec `hugo server`, Hugo gÃ©nÃ¨re le fichier en mÃ©moire, il n'est donc pas disponible sur le disque.
