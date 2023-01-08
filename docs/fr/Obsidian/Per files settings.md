---
title: Paramètre par fichier
---


## Changer de dépôt

:sparkles: Il est maintenant possible de configurer un dépôt à partir du frontmatter avec la clé `repo` !
> [!warning] Attention
> - Le token GitHub doit avoir les droits d'écriture sur le dépôt.
> - Les fonctions globales (tel que `partager toutes les notes` ou encore `partager toutes les notes éditées`) ignorerons les fichiers envoyés dans un autre dépôt que celui configuré dans les paramètres du plugin.
> - L'[auto-nettoyage](#auto-nettoyage) sur ce dépôt fonctionnera sur ce dépôt lors de l'envoie d'une note configurée avec la clé. Vous pouvez le désactiver en ajoutant la clé `autoclean: false` dans le frontmatter.
> - La clé doit être écrite dans cet ordre : `repo: pseudo_github/nom_du_dépôt/branch`, `repo: pseudo_github/nom_du_dépôt` et enfin, `repo: nom_du_dépôt`.
>  Il est cependant possible d'utiliser un objet YAML tel que : 
>  ```yaml
>  repo:
>    owner: pseudo_github
>    repo: nom_du_dépôt
>    branch: branch
>  ```
> Globalement, si vous partagez uniquement un seul fichier, toutes les fonctions habituelles seront faites sur ce dépôt.
> De plus, les paramètres de configuration (dossier, image) seront les mêmes que ceux du dépôt configuré dans les paramètres du plugin (sauf si vous les modifiez dans le frontmatter).

Vous pouvez aussi maintenant envoyer un fichier sur plusieurs dépôts en utilisant la clé `mulitpleRepo` dans le frontmatter. Vous pouvez utiliser un tableau YAML ou une chaîne de caractère séparée par des virgules.
> [!example] Exemple
> ```yaml
> multipleRepo:
>  - repo: nom_du_dépôt
>    owner: pseudo_github
>    branch: main
>  - repo: nom_du_dépôt2
>    owner: pseudo_github2
>    branch: main
> ```
> Il est aussi possible d'utiliser une chaîne de caractère séparée par des virgules.

> [!note] 
> - Par défaut, l'auto-nettoyage est désactivé sur tous les dépôts. Vous pouvez l'activer en ajoutant la clé `autoclean: true` dans le frontmatter pour chaque dépôt individuellement.
> - La clé `multipleRepo` peut être utilisé pour un seul dépôt.


## Explications des clés

Certains paramètres peuvent être écrasés par le frontmatter. Voici la liste des clés disponibles :
1. Pour la conversion des liens, en utilisant la clé `links`, vous pouvez créer un objet YAML tel que :
   - `mdlinks` : Pour convertir les liens wikilinks en liens markdown.
   - `convert` ou `links` : Pour retirer les liens internes et ne garder que le text alternatif ou le nom du fichier.
   - `internals` : Converti les liens internes pour qu'ils correspondent à leur chemin dans le dépôt, sous forme de liens relatifs. S'il est désactivé, les liens seront conservés tel quel.
   - `nonShared` : Comme au-dessus, mais pour les liens pointant vers des fichiers non-partagés. S'il est désactivé, les liens seront résumés au nom du fichier.
   Chaque clé est utilisable séparément, en dehors de l'objet YAML.
2. Pour les paramètres d'embed, en utilisant la clé `embed` : 
   - `send: false` désactive l'envoie des notes transclues.
   - `remove: true` supprime toute mention des notes translues.
   Comme auparavant, chaque clé est utilisable séparément, en dehors de l'objet YAML. `embed: false` empêche l'envoie, et `removeEmbed : true` supprime les mentions.
3. `attachment` modifie les options pour les pièces jointes :
   - `send: false` désactive l'envoie des pièces jointes.
   - `folder` permet de changer le dossier de destination des pièces jointes. Ce paramètre peut avoir des effets indésirables avec le paramètre d'auto-nettoyage.
   Avec une seule clé : `attachmentLinks` pour le dossier, et `attachment: false` pour la désactivation.
4. `dataview` modifie les options pour les paramètres de dataview.
5. `hardBreak` pour les sauts de ligne.
6. `baseLink` pour changer le lien qui sera créé et copier par la fonction de partage de lien.

## En utilisant des objets YAML

```yaml
links:
  mdlinks: boolean #converti en lien markdown
  convert: boolean #transforme les liens en simple string et ne conserve que leur texte alt ou le titre/file name (cela retire le [[]]/[]())
  internals: boolean #converti les liens internes pour correspondre à leur chemin dans le dépôt, sous forme de lien relatif
  nonShared: boolean #converti les liens des fichiers non partagés en lien relatif
embed:
  send: boolean #empêche l'envoie des notes transcluent
  remove: boolean #supprime les citations de note totalement en supprimant entièrement le ![[]] ou ![]() 
attachment: 
  send: boolean #empêche l'envoie des pièces-jointes
  folder: string #change le dossier par défaut
dataview: boolean #permet d'empêcher ou autorise la conversion des dataviews queries
hardbreak: boolean #écrase le paramètres pour les hard space en markdown.
repo: 
  branch: string #change la branche
  repo: string #change le dépôt
  owner: string #change le propriétaire (c'est votre nom d'utilisateur Github)
auto: boolean #désactive le nettoyage automatique
baselink: string #change le lien de base pour les paramètres de copie de lien
```

Pour plusieurs dépôts :

```yaml
links:
  mdlinks: boolean #converti en lien markdown
  convert: boolean #transforme les liens en simple string et ne conserve que leur texte alt ou le titre/file name (cela retire le [[]]/[]())
embed:
  send: boolean #empêche l'envoie des notes transcluent
  remove: boolean #supprime les citations de note totalement en supprimant entièrement le ![[]] ou ![]() 
attachment: 
  send: boolean #empêche l'envoie des pièces-jointes
  folder: string #change le dossier par défaut
dataview: boolean #permet d'empêcher ou autorise la conversion des dataviews queries
hardbreak: boolean #écrase le paramètres pour les hard space en markdown.
baselink: string #change le lien de base pour les paramètres de copie de lien
multipleRepo: 
  - repo:
      branch: string #change la branche
      repo: string #change le dépôt
      owner: string #change le propriétaire (c'est votre nom d'utilisateur Github)
      autoclean: boolean #active le nettoyage automatique
  - repo:
      branch: string #change la branche
      repo: string #change le dépôt
      owner: string #change le propriétaire (c'est votre nom d'utilisateur Github)
      autoclean: boolean #active le nettoyage automatique
```
## En utilisant les noms simples

```yaml
links: boolean #transforme les liens en simple string et ne conserve que leur texte alt ou le titre/file name (cela retire le [[]]/[]())
mdlinks: boolean #converti en lien markdown
internals: boolean #converti les liens internes pour correspondre à leur chemin dans le dépôt, sous forme de lien relatif
nonShared: boolean #converti les liens des fichiers non partagés en lien relatif
embed: boolean #empêche l'envoie des notes transcluent
removeEmbed: boolean #supprime les citations de note totalement en supprimant entièrement le ![[]] ou ![]()
attachmentLinks: string #change le dossier des pièces-jointes par défaut
attachment: boolean #empêche l'envoie des pièces-jointes
dataview: boolean #permet d'empêcher ou autorise la conversion des dataviews queries
hardbreak: boolean #écrase le paramètres pour les hard space en markdown.
repo: string #owner/repo/branch ou owner/repo or repo
autoclean: boolean #active le nettoyage automatique
baselink: string #change le lien de base pour les paramètres de copie de lien
```

Pour plusieurs dépôts :
```yaml
links: boolean #transforme les liens en simple string et ne conserve que leur texte alt ou le titre/file name (cela retire le [[]]/[]())
mdlinks: boolean #converti en lien markdown
embed: boolean #empêche l'envoie des notes transcluent
removeEmbed: boolean #supprime les citations de note totalement en supprimant entièrement le ![[]] ou ![]()
attachmentLinks: string #change le dossier des pièces-jointes par défaut
attachment: boolean #empêche l'envoie des pièces-jointes
dataview: boolean #permet d'empêcher ou autorise la conversion des dataviews queries
hardbreak: boolean #écrase le paramètres pour les hard space en markdown.
baselink: string #change le lien de base pour les paramètres de copie de lien
multipleRepo:
    - string #owner/repo/branch/autoclean ou owner/repo/branch ou owner/repo ou repo
    - string #owner/repo/branch/autoclean ou owner/repo/branch ou owner/repo ou repo
```

Les valeurs par défauts sont dérivés de vos paramètres (`settings.clé` se réfère à eux)

```yaml
links:
  mdlinks: settings.wikilinks
  convert: true
  internals: settings.internals_links
  nonShared: settings.non_shared_links
embed: 
  send: settings.embed
  remove: false
attachment:
  send: settings.attachment
  folder: settings.default_folder_image || settings.default_folder || filepath
dataview: settings.dataview
hardbreak: settings.hardbreak
repo: #multipleRepo utilise les mêmes paramètres
  branch: settings.branch
  repo: settings.repo
  owner: settings.owner
autoclean: settings.auto_clean
baselink: string #change le lien de base pour les paramètres de copie de lien
```

