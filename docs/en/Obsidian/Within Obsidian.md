---
share: true
title: Warning
---

>[!note] 
> The github actions will only convert hashtags and convertion to Admonition mkdocs callouts. Now, two mkdocs plugin handle this, so you don't need (normally) to use obs2mk in minimal configuration anymore. 
>
>The plugins are :
>- [Mkdocs Callouts](https://github.com/sondregronas/mkdocs-callouts)
>- [Custom Tags Attributes](https://github.com/lisandra-dev/mkdocs-custom-tags-attributes)
>
> These two plugin will never change the file send in Github, because the edition happend during the page build. 

The plugin directly edit :
- [[Template/customization#Folder note|Folder note]]
- Categorization and custom tree creation

>[!warning] If you use your vault directly in a repo, the send will break your files! The script is not for theses strategies.

You can delete/disable safely the workflow named `ci.yml`, `manual_run.yml` and edit the `mkdocs_build.yml` to remove the `if:` line ([at the l18 lines](https://github.com/obsidianPublisher/obsidian-mkdocs-publisher-template/blob/bff6d23ddf27064c39a2696159ad25e4a9554d3d/.github/workflows/mkdocs_build.yml#L18)).