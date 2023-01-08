---
share: true
title: Snippets et outils
---

En travaillant sur mon blog, j'ai créé quelques snippets sympas ou outils utiles.

## Snippets CSS
### Extraits CSS de la grille

Convertir automatiquement le [grid callout layout (de ITS)](https://github.com/SlRvb/Obsidian--ITS-Theme/blob/main/S%20-%20Callouts.css) en mkdocs

![[.../assets/img/example_grid_layout.png]]

Ajoutez ceci à n'importe quel fichier css :

```css
:root {
    --md-admonition-icon--grid: url('data:image/svg+xml;charset=utf-8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 640 512"><path d="M352 432c0 8.836-7.164 16-16 16H176c-8.838 0-16-7.164-16-16V128H48c-26.51 0-48 21.5-48 48v288c0 26.51 21.49 48 48 48h416c26.51 0 48-21.49 48-48v-80H352v48zm-248 7c0 4.969-4.031 9-9 9H65c-4.969 0-9-4.031-9-9v-30c0-4.969 4.031-9 9-9h30c4.969 0 9 4.031 9 9v30zm0-104c0 4.969-4.031 9-9 9H65c-4.969 0-9-4.031-9-9v-30c0-4.969 4.031-9 9-9h30c4.969 0 9 4.031 9 9v30zm0-104c0 4.969-4.031 9-9 9H65c-4.969 0-9-4.031-9-9v-30c0-5 4.03-9 9-9h30c4.969 0 9 4.031 9 9v30zm304 178c0-4.969 4.031-9 9-9h30c4.969 0 9 4.031 9 9v30c0 4.969-4.031 9-9 9h-30c-4.969 0-9-4.031-9-9v-30zM591.1 0h-352c-25.6 0-48 21.49-48 48v256c0 26.51 21.49 48 48 48h352c26.51 0 48-21.49 48-48V48c.9-26.51-20.6-48-48-48zm-288 64c17.68 0 32 14.33 32 32s-14.32 32-32 32c-16.8 0-32-14.3-32-32s15.2-32 32-32zm271 215.6c-2.8 5.2-8.2 8.4-14.1 8.4H271.1c-6 0-10.6-3.4-13.4-8.7-2.7-5.4-2.2-11.9 1.4-16.7l70-96c3-4.2 7.8-6.6 12-6.6 5.11 0 9.914 2.441 12.93 6.574l22.35 30.66 62.74-94.11C442.1 98.67 447.1 96 453.3 96c5.348 0 10.34 2.672 13.31 7.125l106.7 160c3.29 4.875 3.59 11.175.79 16.475z"/></svg>');
}

.md-typeset .admonition.grid {
    box-shadow: none;
}

.md-typeset .admonition.grid p:not(.admonition-title) {
    display: flex;
    margin-block-start: 0;
    margin-block-end: 0;
    justify-content: center;
}

.md-typeset .admonition.grid img {
    display: table-cell;
    vertical-align: middle;
    padding: 1px;
    width: 75%;
    height: 75%;
}
```

### Ajouter une bannière sur votre blog

![image](https://user-images.githubusercontent.com/30244939/163732766-d08b102f-508b-496e-a99f-68f865b2080b.png)

Vous pouvez ajouter une bannière d'image cool avec l'édition du fichier `assets/css/customization.css`.

```css
.md-header,
.md-nav--primary .md-nav__title[for="__drawer"] {
    background: var(--md-primary-fg-color) url(image_links) left center/cover no-repeat;
}
```
N'oubliez pas d'éditer le `image_link` avec les vrais liens ! Personnellement, j'utilise une image unsplash.

## Plugins

> [!note] Requirements
> N'oubliez pas d'ajouter le plugin dans votre `requirements.txt`.

### Custom fences
> [!info] Fourni avec le modèle

Certains plugins d'Obsidian utilisent des codeblocks pour faire certaines choses, comme [Agtable] (https://github.com/windily-cloud/obsidian-AGtable) ou [Table extended] (https://github.com/aidenlx/table-extended).

Pour convertir automatiquement ces blocs en markdown, j'utilise un mini plugin que j'ai écrit : [Mkdocs Custom Fence](https://github.com/lisandra-dev/mkdocs_custom_fences)
Pour l'utiliser :
- Ajouter `mkdocs_custom_fences` dans votre [requirements.txt](https://github.com/ObsidianPublisher/obsidian-mkdocs-publisher-template/blob/main/requirements.txt)
- Modifiez le fichier [mkdocs.yml](https://github.com/ObsidianPublisher/obsidian-mkdocs-publisher-template/blob/d7b7d43ff237c09e0cbf160889dcdac4b9459dfd/mkdocs.yml#L70) comme suit : 
  ```yml
  markdow_extensions :
  pymdownx.superfences :
      custom_fences :
        - nom : md-render
          classe : md-render
          format : !!python/name:mkdocs_custom_fences.md_render.md_sub_render
  ```

Par exemple, pour AGtable : 
```yml
  - pymdownx.superfences :
      custom_fences :
        - nom : agtable
          classe : agtable
          format : !!python/name:mkdocs_custom_fences.md_render.md_sub_render
```

### [Mkdocs Callouts](https://pypi.org/project/mkdocs-callouts/)

> [!info] Fourni avec le modèle

> [!info] Informations sur le plugin
> Un plugin simple qui convertit les callouts de style Obsidian et les transforme en Admonitions supportées par mkdocs.
> - *Lien* : https://pypi.org/project/mkdocs-callouts/
> - *Installation* : `pip install mkdocs-callouts`


### Page chiffrée

> [!note] La configuration de base pour Material et de ce modèle est déjà incluse dans le fichier `mkdocs.yml` et dans `utils.css`.

> [!info] Informations sur le plugin
> Ce plugin vous permet d'avoir des articles et des pages protégés par un mot de passe dans MKdocs.
> - *Lien* : https://pypi.org/project/mkdocs-encryptcontent-plugin/
> - *Installation* : `pip install mkdocs-encryptcontent-plugin`

Tout d'abord, configurez l'affichage de ce plugin pour mkdocs en ajoutant ceci dans votre css :

```css
[data-md-color-scheme="slate"] #mkdocs-content-password {
    background-color:rgba(0, 0, 0, 0.11)
}

[data-md-color-scheme="default"] #mkdocs-content-password {
    background-color:white;
}

#mkdocs-content-password {
    border-radius: 5px;
    height: 40px;
    width: 50%;
    padding-left: 10px;
}

#mkdocs-decrypt-button {
    border-radius: 5px;
    fill: var(--md-default-fg-color--light);
    height: 30px;
    width: 5%;
}
```

Configurez le `mkdocs.yml` pour ajouter le plugin, comme dit dans le README.

> [!example] Exemple
> Cette configuration permet de mémoriser le mot de passe et d'utiliser un mot de passe par page. 
> ```yml
> plugins:
> 	- encryptcontent:
> 	     title_prefix: '🔐 '
> 	     summary: 'Private page'
> 	     placeholder: 'Password'
> 	     decryption_failure_message: 'Invalid!!'
> 	     encryption_info_message: "You don't have access to this page without password"
> 	     remember_password: True
> 	     search_index: 'encrypted' #Material doesn't support dynamicaly encryption search
> 	     password_button: True
> 	     password_button_text: '<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512" height="1em" width="1em"><path d="M416 32h-64c-17.67 0-32 14.33-32 32s14.33 32 32 32h64c17.67 0 32 14.33 32 32v256c0 17.67-14.33 32-32 32h-64c-17.67 0-32 14.33-32 32s14.33 32 32 32h64c53.02 0 96-42.98 96-96V128C512 74.98 469 32 416 32zM342.6 233.4l-128-128c-12.51-12.51-32.76-12.49-45.25 0c-12.5 12.5-12.5 32.75 0 45.25L242.8 224H32C14.31 224 0 238.3 0 256s14.31 32 32 32h210.8l-73.38 73.38c-12.5 12.5-12.5 32.75 0 45.25s32.75 12.5 45.25 0l128-128C355.1 266.1 355.1 245.9 342.6 233.4z"/></svg>'
> ```
> Mais vous pourriez aussi soutenir une documentation entièrement cryptée
> ```yml
> plugins:
>    - encryptcontent:
>        global_password: 'votre_mot_de_passe'
> 
>```

Pour ajouter une page unique chiffrée, il suffit d'ajouter `password : your_secret_password` dans votre fichier markdown.


> [!warning] Sécurité
> Évidemment, si vous l'utilisez dans un dépôt public, il est totalement inutile d'ajouter cette sécurité (le fichier peut être consulté uniquement sur GitHub). N'utilisez pas ce plugin pour partager des informations sensibles !


## Custom tags attributes
> [!info] Fourni avec le modèle

> [!info] Custom tags attribute
> Ajouter [attribute list](https://python-markdown.github.io/extensions/attr_list/) en utilisant simplement des tags dans vos textes.
> *Lien:* [Custom tags attributes](https://pypi.org/project/mkdocs-custom-tags-attributes/)
> *Installation:* `pip install mkdocs-custom-tags-attributes`

