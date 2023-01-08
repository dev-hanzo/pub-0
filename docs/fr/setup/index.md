---
title: Plugin inclus
share: true
---

Le fichier `mkdocs.yml` contient également la configuration de [Mkdocs Plugin](https://www.mkdocs.org/dev-guide/plugins/). Si vous ajoutez le plugin, vous **devez** l'ajouter à votre `requirements.txt` car la build l'utilise pour construire le blog.

J'ai inclus :
- [Ezlinks (depuis mkdocs-ezlinked-plugin)](https://pypi.org/project/mkdocs-ezlinked-plugin/) : Pour supporter les wikilinks
- [Mermaid2](https://github.com/fralau/mkdocs-mermaid2-plugin)
- [Awesome pages](https://github.com/lukasgeiter/mkdocs-awesome-pages-plugin)
- [Embed File](https://github.com/lisandra-dev/mkdocs_embed_file_plugins), pour obtenir les transclusions comme dans Obsidian (avec la syntaxe `![](file)` ou `![[file]]`)
- [Git revision date localized](https://github.com/timvink/mkdocs-git-revision-date-localized-plugin), pour obtenir la date de création/edition des fichiers, via git.
- [Mkdocs Simple Hooks](https://pypi.org/project/mkdocs-simple-hooks/), qui permet de créer des scripts python pour mkdocs (y compris l'édition de modèles jinja!).
- [Mkdocs Encrypt Contents](https://github.com/CoinK0in/mkdocs-encryptcontent-plugin) qui permet de cacher des fichiers du site. Veuillez lire [[Template/snippets and tools#Page encrypted|See here]] pour plus d'informations.
- [Mkdocs Callout](https://pypi.org/project/mkdocs-callouts/)
- [Custom tags attributes](https://pypi.org/project/mkdocs-custom-tags-attributes/)