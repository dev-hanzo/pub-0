---
share: true
title: Avertissement
---

>[!note] 
> Les actions github ne convertissent plus les hashtags et la conversion vers les callouts Admonition mkdocs. Maintenant, deux plugins mkdocs gèrent cela, donc vous n'avez plus besoin (normalement) d'utiliser obs2mk.
>
> Les plugins sont :
> - [Mkdocs Callouts](https://github.com/sondregronas/mkdocs-callouts)
> - [Custom Tags Attributes](https://github.com/lisandra-dev/mkdocs-custom-tags-attributes)
>
> Ces deux plugins ne changeront jamais le fichier envoyé dans Github, car l'édition a lieu pendant la construction de la page. 


Le plugin modifie directement :
- [[Template/customization#Folder note|Folder note]]
- Catégorisation et création des chemins de fichiers personnalisés

>[!warning] Si vous utilisez votre coffre-fort directement dans un dépôt, l'envoi cassera vos fichiers ! Le module n'est pas pour ces stratégies.
