---
title: Modules utiles
share: true
---

**Some useful plugin to support the script** : 
- [Metacopy](https://github.com/lisandra-dev/obsidian-metacopy)
- [Commander](https://github.com/phibr0/obsidian-commander)    
- [Alx Folder Note](https://github.com/aidenlx/alx-folder-note)
- Custom Attribute :
	- [CM6 Live Preview](https://github.com/nothingislost/obsidian-cm6-attributes) ; 
	- [Markdown Attribute](https://github.com/valentine195/obsidian-markdown-attributes)
	- [Contextual Typography](https://github.com/mgmeyers/obsidian-contextual-typography) 

## Metacopy
En utilisant [metacopy](https://github.com/lisandra-dev/obsidian-metacopy) vous pouvez rapidement copier un lien vers une page partagée
Pour créer un lien, vous devez configurer :  
 1. `category` dans `key`  
 2. Ajoutez votre `set_url` dans `base link`.  
 3. Ajoutez `category` dans le lien `key`.  
  
En outre, vous pouvez supprimer la métacopie de votre menu fichier en utilisant une clé de métadonnée, de sorte que vous pouvez activer la métacopie seulement pour `share : true`. Metacopy supporte également le [[en/index#folder-note|folder note]].

La configuration finale de metacopy pour mkdocs_obsidian sera :  

![1](https://i.imgur.com/mZvzl6Z.png)  
![picture 2](https://i.imgur.com/CMt9fQj.png)  

Ainsi, au final, un menu apparaîtra sur le fichier avec `share : true` et une `category` configurée. Ce menu se trouve sur le clic gauche et le menu fichier. Vous pouvez rapidement copier un lien à partir de là, comme un lien de partage Google ou notion !  

## Front matter template

```yml
title:  
share: 
description:  
category:
```
