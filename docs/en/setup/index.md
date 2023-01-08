---
title: Plugins included
share: true
---

### Plugins

The `mkdocs.yml` also contains the configuration for [Mkdocs Plugin](https://www.mkdocs.org/dev-guide/plugins/). If you add plugin, you **need** to add it to your `requirements.txt` because the build use it to construct the blog.

I included :
- [Ezlinks (from mkdocs-ezlinked-plugin)](https://pypi.org/project/mkdocs-ezlinked-plugin/) : to support directly wikilinks
- [Mermaid2](https://github.com/fralau/mkdocs-mermaid2-plugin)
- [Awesome pages](https://github.com/lukasgeiter/mkdocs-awesome-pages-plugin)
- [Embed File](https://github.com/lisandra-dev/mkdocs_embed_file_plugins), to support embedding file as in Obsidian (with the `![](file)` or `![[file]]` syntax)
- [Git revision date localized](https://github.com/timvink/mkdocs-git-revision-date-localized-plugin), to add a date listing 
- [Mkdocs Simple Hooks](https://pypi.org/project/mkdocs-simple-hooks/), to allow creating simple python script for mkdocs (including jinja template editing!). 
- [Mkdocs Encrypt Contents](https://github.com/CoinK0in/mkdocs-encryptcontent-plugin) will allow you to "hide" file in the site. [[Template/snippets and tools#Page encrypted|See here]] for more information.
- [Mkdocs Callout](https://pypi.org/project/mkdocs-callouts/)
- [Custom tags attributes](https://pypi.org/project/mkdocs-custom-tags-attributes/)

> [!info] Superfences & dataviewjs
> You will spot that I added a [`custom fences`](https://facelessuser.github.io/pymdown-extensions/extensions/superfences/) for dataviewjs. Sorry, dataviewjs is not currently supported by mkdocs nor Obsidian Publisher. This custom fences will hide every dataviewjs block. 
> It will, so, prevent display stange block in your markdown file. If you need to display it as code, change the language (like `js` for example).

