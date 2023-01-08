---
title: Filepath example 
---

In this file, I add a list of example for the filepath settings, edited by your **Upload configuration**.

## Folder configuration
### Metadata frontmatter

> [!EXAMPLE] Example
> - You use `category` in a file with `category: Roleplay/Characters/DND`  
> - You set a root folder with `_docs/pages`  
> - And you set a default folder on `_docs/draft`  
>	  
> The final path (in GitHub!) will be : `_docs/pages/Roleplay/Characters/DND`  
>	  
> But, if you don't set `category`, the path will be `_docs/draft`  

### Fixed folder

> [!example] Example
> - If you set `source` for the default folder, any file will be sent in `your_repo/source`, whatever is their frontmatter key or their relative path.
> - If you leave it blank, it will be sent in `your_repo` directly.

### Obsidian Path

> [!example] Example
> For a file in `20. Compendium/DND/Monster`
> - If you set `source` :  the final path will be `source/20. Compendium/DND/Monster`
> - If you leave the default folder blank, the final path will be `20. Compendium/DND/Monster`

> [!example] Removing a subpath
> You can use this option to designate a subfolder as the "vault" for syncing the repository.
> You could plug in `vault/sub` as the path removed. The sync will flow `vault/sub` as `repo`. 
> A file in `vault/sub/folderA` will be sync in `repo/folderA`

## Changing the filename 

> [!example] Using a frontmatter key `title`
> `title: My title`
> `filename` : `28-03-2020-1845.md`
> Final filename : `My title.md`

## Links & folder notes


> [!example] frontmatter example with a file named `folder2`
> - Using a category value : `folder1/folder2` 
> - With root value named `docs` ⇒ `docs/folder1/folder2/index.md`
> - Without root : `folder1/folder2/index.md` 
> - Without category value, with default folder named `drafts` : `draft/folder2.md` (the name won't be converted!)

> [!example] Example with Obsidian Path & a file named `folder2`
> With a path like : `folder1/folder2` the new path will be :
> - If you use a default folder named `docs` : `docs/folder1/folder2/index.md`
> - Without : `folder1/folder2/index.md`

## Internal links

> [!example] 
> Cited file : `docs/XX/YY/my_file.md`
> File to convert : `docs/XX/ZZ/new_file.md`
> Path created : `../YY/my_file.md`
