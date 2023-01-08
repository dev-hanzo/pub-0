---
title: Filepath example 
---

Dans ce fichier, j'ajoute une liste d'exemple pour les paramètres du chemin de fichier, édité par votre configuration d'**Upload**.

## Configuration de dossier
### En utilisant les métadonnées

> [!EXAMPLE] Par exemple
> - Vous utilisez `category` dans un fichier avec `category : JDR/Personnages/DND`
> - Vous définissez un dossier racine avec `_docs/pages`.  
> - Vous définissez un dossier par défaut sur `_docs/draft`  
>	  
> Le chemin final (dans GitHub !) sera : `_docs/pages/JDR/Personnages/DND`  
>	  
> Mais, si vous ne mettez pas `category`, le chemin sera `_docs/draft`.  


### Dossier fixée

> [!example] Par exemple
> - Si vous définissez `source` pour le dossier par défaut, tout fichier sera envoyé dans `votre_repo/source`, quelque soit sa clé frontmatter ou son chemin relatif.
> - Si vous le laissez vide, il sera envoyé directement dans `votre_repo`.

### Chemin obsidian

> [!example] Par exemple
> Pour un fichier dans `20. Compendium/DND/Créature`
> - Si vous définissez `source` : le chemin final sera `source/20. Compendium/DND/Créature`.
> - Si vous laissez le dossier par défaut vide, le chemin final sera `20. Compendium/DND/Créature`

> [!example] Synchroniser un sous-dossier
> Vous pouvez utiliser cette option pour désigner un sous-dossier comme "coffre-fort" pour la synchronisation du dépôt.
> Vous pourrez utiliser `vault/sub` comme le chemin retiré. L'envoie passera par `vault/sub` comme racine dans le dépôt. 
> Un fichier dans `vault/sub/dossierA` sera envoyé dans `repo/dossierA`.

## Changer le nom du fichier

> [!example] En utilisant la clé `title`
> `title: Mon titre`
> `filename` : `28-03-2020-1845.md`
> Chemin final : `Mon titre.md`

## Links & folder notes


> [!example] Exemple de frontmatter avec un fichier nommé `folder2`
> - Avec une valeur de catégorie : `dossier1/dossier2` 
> - Avec une valeur racine nommée `docs` ⇒ `docs/folder1/folder2/index.md`
> - Sans valeur racine : `folder1/folder2/index.md` 
> - Sans valeur de catégorie, avec un dossier par défaut nommé `drafts` : `draft/folder2.md` (le nom ne sera pas converti !)


> [!example] Exemple avec le chemin Obsidian et un dossier nommé `folder2`
> Avec un chemin comme : `dossier1/dossier2` le nouveau chemin sera :
> - Si vous utilisez un dossier par défaut nommé `docs` : `docs/folder1/folder2/index.md`
> - Sans : `folder1/folder2/index.md`


## Liens internes

> [!example] 
> Fichier cité : `docs/XX/YY/mon_fichier.md`.
> Fichier à convertir : `docs/XX/ZZ/new_file.md`.
> Chemin créé : `../YY/mon_fichier.md`.
