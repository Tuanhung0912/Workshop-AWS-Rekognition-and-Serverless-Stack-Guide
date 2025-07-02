---
date: 2024-06-17
title: Personnalisation du style
weight: 25
---

**Hugo-theme-learn** a Ã©tÃ© conÃ§u pour Ãªtre aussi configurable que possible en dÃ©finissant plusieurs [partials](https://gohugo.io/templates/partials/)

Dans `themes/hugo-theme-learn/layouts/partials/`, vous pourrez trouver tous les *partials* dÃ©finis pour ce thÃ¨me. Si vous avez besoin d'Ã©craser quelque chose, ne modifiez pas le code directement. A la place, [suivez cette page](https://gohugo.io/themes/customizing/). Vous crÃ©erez alors un nouveau *partial* dans le dossier `layouts/partials` de votre site local. Ce *partial* aura la prioritÃ©.

Ce thÃ¨me dÃ©finit les *partials* suivant :

- *header*: l'en-tÃªte de la page page (contient le fil d'Ariane). _Pas vouÃ© Ã  Ãªtre Ã©crasÃ©_
- *custom-header*: En-tÃªte personnalisÃ©. VouÃ© Ã  Ãªtre Ã©crasÃ© quand vous ajoutez des imports CSS. N'oubliez pas d'inclure la balise HTML `style` dans votre fichier
- *footer*: le pied-de-page de la page (contains les flÃ¨ches). _Pas vouÃ© Ã  Ãªtre Ã©crasÃ©_
- *custom-footer*:  Pied-de-page personnalisÃ©. VouÃ© Ã  Ãªtre Ã©crasÃ© quand vous ajoutez du Javascript. N'oubliez pas d'inclure la balise HTML `javascript` dans votre fichier
- *favicon*: le favicon
- *logo*: le logo, affichÃ© un haut Ã  gauche.
- *meta*: les balises HTML meta, que vous pouvez Ã©craser sans problÃ¨me.
- *menu*: Le menu Ã  gauche. _Pas vouÃ© Ã  Ãªtre Ã©crasÃ©_
- *menu-footer*: Le pied-de-page du menu
- *search*: le champ de recherche
- *toc*: le sommaire

## Changer le logo

CrÃ©ez un nouveau fichier dans `layouts/partials/`, nommÃ© `logo.html`. Puis, Ã©crivez le code HTML voulu.
Vous pourriez utiliser une balise HTML `img` et rÃ©fÃ©rencer une image crÃ©Ã©e dans le dossier *static*, voire mÃªme y coller un code SVG !

{{% notice note %}}
La taille du logo va s'adapter automatiquement
{{% /notice %}}

## Changer le favicon

Si votre favicon est un png, dÃ©posez votre image dans votre dossier local `static/images/` et nommez le `favicon.png`

Si vous avez besoin de changer ce comportement par dÃ©faut, crÃ©er un nouveau fichier dans `layouts/partials/` et nommez le `favicon.html`. Puis ajoutez quelque chose comme:

```html
<link rel="shortcut icon" href="/images/favicon.png" type="image/x-icon" />
```

## Changer les couleurs par dÃ©faut {#theme-variant}

**Hugo Learn theme** vous permet de choisir nativement entre 3 schÃ©ma de couleurs, mais n'hÃ©sitez pas Ã  en ajouter d'autres ! Les couleurs par dÃ©faut sont celles de [Grav Learn Theme](https://learn.getgrav.org/).

### Variante rouge

```toml
[params]
  # Modifier le schÃ©ma de couleur par dÃ©faut. Peut Ãªtre "red", "blue", "green".
  themeVariant = "red"
```

![Variante rouge](/en/basics/style-customization/images/red-variant.png?width=60pc)

### Variante bleue

```toml
[params]
  # Modifier le schÃ©ma de couleur par dÃ©faut. Peut Ãªtre "red", "blue", "green".
  themeVariant = "blue"
```

![Variante bleue](/en/basics/style-customization/images/blue-variant.png?width=60pc)

### Variante verte

```toml
[params]
  # Modifier le schÃ©ma de couleur par dÃ©faut. Peut Ãªtre "red", "blue", "green".
  themeVariant = "green"
```

![Variante verte](/en/basics/style-customization/images/green-variant.png?width=60pc)

### Votre variante

PremiÃ¨rement, crÃ©ez un nouveau fichier CSS dans votre dossier `static/css`, prÃ©fixÃ© par `theme` (ex: avec le theme_lemien_ `static/css/theme-lemien.css`). Copiez le contenu suivant et modifiez les couleurs dans les variables CSS.

```css

:root{
    
    --MAIN-TEXT-color:#323232; /* Color of text by default */
    --MAIN-TITLES-TEXT-color: #5e5e5e; /* Color of titles h2-h3-h4-h5 */
    --MAIN-LINK-color:#1C90F3; /* Color of links */
    --MAIN-LINK-HOVER-color:#167ad0; /* Color of hovered links */
    --MAIN-ANCHOR-color: #1C90F3; /* color of anchors on titles */

    --MENU-HEADER-BG-color:#1C90F3; /* Background color of menu header */
    --MENU-HEADER-BORDER-color:#33a1ff; /*Color of menu header border */ 

    --MENU-SEARCH-BG-color:#167ad0; /* Search field background color (by default borders + icons) */
    --MENU-SEARCH-BOX-color: #33a1ff; /* Override search field border color */
    --MENU-SEARCH-BOX-ICONS-color: #a1d2fd; /* Override search field icons color */

    --MENU-SECTIONS-ACTIVE-BG-color:#20272b; /* Background color of the active section and its childs */
    --MENU-SECTIONS-BG-color:#252c31; /* Background color of other sections */
    --MENU-SECTIONS-LINK-color: #ccc; /* Color of links in menu */
    --MENU-SECTIONS-LINK-HOVER-color: #e6e6e6;  /* Color of links in menu, when hovered */
    --MENU-SECTION-ACTIVE-CATEGORY-color: #777; /* Color of active category text */
    --MENU-SECTION-ACTIVE-CATEGORY-BG-color: #fff; /* Color of background for the active category (only) */

    --MENU-VISITED-color: #33a1ff; /* Color of 'page visited' icons in menu */
    --MENU-SECTION-HR-color: #20272b; /* Color of <hr> separator in menu */
    
}

body {
    color: var(--MAIN-TEXT-color) !important;
}

textarea:focus, input[type="email"]:focus, input[type="number"]:focus, input[type="password"]:focus, input[type="search"]:focus, input[type="tel"]:focus, input[type="text"]:focus, input[type="url"]:focus, input[type="color"]:focus, input[type="date"]:focus, input[type="datetime"]:focus, input[type="datetime-local"]:focus, input[type="month"]:focus, input[type="time"]:focus, input[type="week"]:focus, select[multiple=multiple]:focus {
    border-color: none;
    box-shadow: none;
}

h2, h3, h4, h5 {
    color: var(--MAIN-TITLES-TEXT-color) !important;
}

a {
    color: var(--MAIN-LINK-color);
}

.anchor {
    color: var(--MAIN-ANCHOR-color);
}

a:hover {
    color: var(--MAIN-LINK-HOVER-color);
}

#sidebar ul li.visited > a .read-icon {
	color: var(--MENU-VISITED-color);
}

#body a.highlight:after {
    display: block;
    content: "";
    height: 1px;
    width: 0%;
    -webkit-transition: width 0.5s ease;
    -moz-transition: width 0.5s ease;
    -ms-transition: width 0.5s ease;
    transition: width 0.5s ease;
    background-color: var(--MAIN-LINK-HOVER-color);
}
#sidebar {
	background-color: var(--MENU-SECTIONS-BG-color);
}
#sidebar #header-wrapper {
    background: var(--MENU-HEADER-BG-color);
    color: var(--MENU-SEARCH-BOX-color);
    border-color: var(--MENU-HEADER-BORDER-color);
}
#sidebar .searchbox {
	border-color: var(--MENU-SEARCH-BOX-color);
    background: var(--MENU-SEARCH-BG-color);
}
#sidebar ul.topics > li.parent, #sidebar ul.topics > li.active {
    background: var(--MENU-SECTIONS-ACTIVE-BG-color);
}
#sidebar .searchbox * {
    color: var(--MENU-SEARCH-BOX-ICONS-color);
}

#sidebar a {
    color: var(--MENU-SECTIONS-LINK-color);
}

#sidebar a:hover {
    color: var(--MENU-SECTIONS-LINK-HOVER-color);
}

#sidebar ul li.active > a {
    background: var(--MENU-SECTION-ACTIVE-CATEGORY-BG-color);
    color: var(--MENU-SECTION-ACTIVE-CATEGORY-color) !important;
}

#sidebar hr {
    border-color: var(--MENU-SECTION-HR-color);
}
```

Puis, configurez le paramÃ¨tre `themeVariant` avec le nom de votre variante. C'est tout !

```toml
[params]
  # Modifier le schÃ©ma de couleur par dÃ©faut. Peut Ãªtre "red", "blue", "green".
  themeVariant = "lemien"
```
