---
date: 2024-06-17
title: Organisation des pages
weight: 5
---

Dans **Hugo**, les pages sont le cÅ“ur de votre site. Une fois configurÃ©es, les pages sont la valeur ajoutÃ©e de votre site de documentation.

## Dossiers

Organisez votre site comme n'importe quel autre [projet Hugo](https://gohugo.io/content/organization/). Typiquement, vous allez avoir un dossier *content* avec vos pages.

    content
    â”œâ”€â”€ niveau-un 
    â”‚   â”œâ”€â”€ niveau-deux
    â”‚   â”‚   â”œâ”€â”€ niveau-trois
    â”‚   â”‚   â”‚   â”œâ”€â”€ niveau-quatre
    â”‚   â”‚   â”‚   â”‚   â”œâ”€â”€ _index.md       <-- /niveau-un/niveau-deux/niveau-trois/niveau-quatre
    â”‚   â”‚   â”‚   â”‚   â”œâ”€â”€ page-4-a.md     <-- /niveau-un/niveau-deux/niveau-trois/niveau-quatre/page-4-a
    â”‚   â”‚   â”‚   â”‚   â”œâ”€â”€ page-4-b.md     <-- /niveau-un/niveau-deux/niveau-trois/niveau-quatre/page-4-b
    â”‚   â”‚   â”‚   â”‚   â””â”€â”€ page-4-c.md     <-- /niveau-un/niveau-deux/niveau-trois/niveau-quatre/page-4-c
    â”‚   â”‚   â”‚   â”œâ”€â”€ _index.md           <-- /niveau-un/niveau-deux/niveau-trois
    â”‚   â”‚   â”‚   â”œâ”€â”€ page-3-a.md         <-- /niveau-un/niveau-deux/niveau-trois/page-3-a
    â”‚   â”‚   â”‚   â”œâ”€â”€ page-3-b.md         <-- /niveau-un/niveau-deux/niveau-trois/page-3-b
    â”‚   â”‚   â”‚   â””â”€â”€ page-3-c.md         <-- /niveau-un/niveau-deux/niveau-trois/page-3-c
    â”‚   â”‚   â”œâ”€â”€ _index.md               <-- /niveau-un/niveau-deux
    â”‚   â”‚   â”œâ”€â”€ page-2-a.md             <-- /niveau-un/niveau-deux/page-2-a
    â”‚   â”‚   â”œâ”€â”€ page-2-b.md             <-- /niveau-un/niveau-deux/page-2-b
    â”‚   â”‚   â””â”€â”€ page-2-c.md             <-- /niveau-un/niveau-deux/page-2-c
    â”‚   â”œâ”€â”€ _index.md                   <-- /niveau-un
    â”‚   â”œâ”€â”€ page-1-a.md                 <-- /niveau-un/page-1-a
    â”‚   â”œâ”€â”€ page-1-b.md                 <-- /niveau-un/page-1-b
    â”‚   â””â”€â”€ page-1-c.md                 <-- /niveau-un/page-1-c
    â”œâ”€â”€ _index.md                       <-- /
    â””â”€â”€ premiere-page.md                <-- /premiere-page

{{% notice note %}}
Le fichier `_index.md` est obligatoire dans chaque dossier, c'est en quelque sorte votre page d'accueil pour le dossier.
{{% /notice %}}

## Types

**Hugo-theme-learn** dÃ©finit deux types de pages. *DÃ©faut* et *Chapitre*. Les deux sont utilisables Ã  n'importe quel niveau du site, la seule diffÃ©rence est dans l'affichage.

Un **Chapitre** affiche une page vouÃ©e Ã  Ãªtre une introduction pour un ensemble de pages filles. Habituellement, il va seulement contenir un titre et un rÃ©sumÃ© de la section.
Vous pouvez dÃ©finir n'importe quel contenu HTML comme prÃ©fixe de l'entrÃ©e du menu. Dans l'exemple ci-dessous, c'est juste un nombre mais vous pourriez utiliser une [icÃ´ne](https://fortawesome.github.io/Font-Awesome/).

![Page Chapitre](/en/cont/pages/images/pages-chapter.png?width=50pc)

```markdown
+++
title = "DÃ©marrage"
weight = 5
pre = "<b>1. </b>"
chapter = true
+++

### Chapitre 1

# DÃ©marrage

DÃ©couvrez comment utiliser ce thÃ¨me Hugo et apprenez en les concepts
```

Pour dire Ã  **Hugo-theme-learn** de considÃ©rer la page comme un chapitre, configure `chapter=true` dans le Front Matter de la page.

Une page **DÃ©faut** est n'importe quelle autre page.

![Page dÃ©faut](/en/cont/pages/images/pages-default.png?width=50pc)

    +++
    title = "Installation"
    weight = 15
    +++

    The following steps are here to help you initialize your new website. If you don't know Hugo at all, we strongly suggest you to train by following this [great documentation for beginners](https://gohugo.io/overview/quickstart/).

    ## Create your project

    Hugo provides a `new` command to create a new website.

    ```
    hugo new site <new_project>
    ```

**Hugo-theme-learn** fournit des [archÃ©types]({{< relref "cont/archetypes.fr.md" >}}) pour vous aider Ã  crÃ©er ce type de pages.

## Configuration des Front Matter

Chaque page Hugo doit dÃ©finir un [Front Matter](https://gohugo.io/content/front-matter/) dans le format *yaml*, *toml* ou *json*.

**Hugo-theme-learn** utilise les paramÃ¨tres suivant en plus de ceux dÃ©finis par Hugo:

```toml
+++
# Le Sommaire (table of content = toc) est activÃ© par dÃ©faut. Modifier ce paramÃ¨tre Ã  true pour le dÃ©sactiver.
# Note: Le sommaire est toujours dÃ©sactivÃ© pour les chapitres
disableToc = "false"
# Le titre de la page dans le menu sera prÃ©fixÃ© par ce contentu HTML
pre = ""
# Le titre de la page dans le menu sera suffixÃ© par ce contentu HTML
post = ""
# Modifier le type de la page pour changer l'affichage
chapter = false
# Cache la page du menu
hidden = false
# Nom de la personne qui a modifiÃ© la page. Quand configurÃ©, sera affichÃ© dans le pied de page. 
LastModifierDisplayName = ""
# Email de la personne qui a modifiÃ© la page. Quand configurÃ©, sera affichÃ© dans le pied de page.
LastModifierEmail = ""
+++
```

### Ajouter une icÃ´ne Ã  une entrÃ©e du menu

Dans le Front Matter, ajouter un paramÃ¨tre `pre` pour insÃ©rer du code HTML qui s'affichera avant le label du menu. L'exemple ci-dessous utilise l'icÃ´ne de Github.

```toml
+++
title = "Repo Github"
pre = "<i class='fab fa-github'></i> "
+++
```

![Titre avec icÃ´ne](/en/cont/pages/images/frontmatter-icon.png)

### Ordonner les entrÃ©es dans le menu

Hugo permet de modifier facilement [l'ordre des menu](https://gohugo.io/content/ordering/).

La maniÃ¨re la plus simple est de configurer le paramÃ¨tre `weight` avec un nombre.

```toml
+++
title = "Ma page"
weight = 5
+++
```

## Page d'accueil

Pour configurer votre page d'accueil, vous avez trois choix:

1. CrÃ©er une page `_index.md` dans le dossier `content` et remplissez le fichier avec du *contenu Markdown*
2. CrÃ©er une page `index.html` dans le dossier `static` et remplissez le fichier avec du *contenu HTML*
3. Configurez votre serveur pour automatiquement rediriger la page d'accueil vers l'une de vos pages.
