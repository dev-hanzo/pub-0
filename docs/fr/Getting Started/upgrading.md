---
title: Mettre-à-jour le modèle
---

L'utilisation d'un template (à la place de fork) empêche d'obtenir la mise à jour que je fais parfois. Donc, pour garder un œil dessus, vous devez créer une **branche** basée sur la template. 

Dans le dossier cloné, (dans votre blog) faites : 
```
git remote add Template git@github.com:ObsidianPublisher/obsidian-mkdocs-publisher-template.git
git fetch Template
git checkout -b template Template/main
```
Ensuite, pour récupérer la mise à jour : 
```
git checkout template
git pull
```

Vous pouvez fusionner la branche, ou juste récupérer le fichier mis à jour avec la commande checkout : 
```git
git checkout main
git checkout template chemin/vers/le/fichier/quevousvoulez 
```

Il est aussi possible de merge (fusionner) les branches avec : 
```
git checkout main
git merge Template/main
```

N'oubliez pas de commit et de push !
