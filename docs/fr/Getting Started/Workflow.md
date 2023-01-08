---
share: true
title: Github Actions
---

Il y a beaucoup d'actions Github ici ! Tout d'abord, si vous avez besoin d'informations sur ce qu'est une action Github :
> [!cite] Définition
> Les GitHub Actions permettent d'automatiser facilement tous vos flux de travail logiciels, désormais avec un CI/CD de classe mondiale. Construisez, testez et déployez votre code directement depuis GitHub. Faites fonctionner les revues de code, la gestion des branches et le triage des problèmes comme vous le souhaitez[^1].

Je vais tout expliquer, ne paniquez pas ! Comme vous pouvez le voir, ici, les actions github (~ le workflow) sont utilisées pour construire Obsidian To Mkdocs (Ou Mkdocs Obsidian Publisher) en utilisant les fichiers de votre dépôt.

> [!info] Sur les push : `mkdocs_build.yml`
> Le fichier `.github/workflows/mkdocs_build.yml` est utilisé pour construire le site mkdocs.
> Il exécute simplement les installations des exigences et les commandes pour construire la page github.
> Ce workflow ne sera exécuté que pour la branche principale ou master, et si le push inclut des fichiers provenant de :
> - docs
> - requirements.txt
> - README.md
> - overrides
> - mkdocs.yml

> [!info] Chaque jour : `update_requirements.yml` 
> Je l'ai créé parce que le Cache Github a besoin d'une version fixe sur les requirements, mais il arrive régulièrement que je mette à jour certains plugins ou qu'il y ait une nouvelle version de Material Mkdocs. Ainsi, ce workflow ne modifiera le fichier `requirements.txt` uniquement s'il trouve une mise à jour.

> [!info] Activé : `create_index.yml`
> Vous permet de créer rapidement une nouvelle "catégorie" / liste de blogs dans votre dépôt, en créant un nouveau dossier spécifié avec le nom de la catégorie.
> Pour créer une nouvelle catégorie, suivez les étapes ci-dessous :
> 1. Allez dans l'onglet "Actions".
> 2. Cliquez sur "Index creation"
> 3. cliquez sur "Run workflow".
> 4. Remplir le formulaire :
> - **Nom du dossier (*New folder name*)** : Le nom du dossier que vous souhaitez créer, ce sera la "nouvelle catégorie". 
> - **Dossier parent (*The path of the new folder*)** : Le chemin *optionnel* du dossier dans lequel vous voulez créer la nouvelle catégorie. Par exemple, `main_category/draft` créera le dossier `docs/main_category/draft/folder_name`.
> - **Description** : Une description *optionnelle* de la catégorie.
> - Vous pouvez également :
> - **Cacher le TOC (*Hide the toc[^2]*)** dans le fichier d'index
> - **Cacher le panneau de navigation** dans le fichier d'index.
> - Effectuer un **dry-run**: Il ne montrera que le résultat de l'opération, mais ne créera pas le dossier et le fichier d'index.

Vous pouvez également créer une exécution conditionnelle du workflow avec le mot-clé `if`. Par exemple, chaque événement de fusion sera précédé de `[PUBLISHER]`. Vous pouvez aussi créer un flux de travail basé sur une "pull request".

> [!info] En utilisant le mot-clé if 
> Ciblez le nom de l'événement de fusion avec : `if : startsWith(github.event.head_commit.message, '[PUBLISHER]')`.
> Vous pouvez utiliser le mot-clé `if` pour des étapes ou des jobs entiers. 

> [!info] À propos de l'exécution du workflow
> Si vous utilisez les workflows (*tous* les workflows) sur un dépôt **privé**, vous devez savoir que vous avez *seulement* 2000 minutes (3000 avec un compte pro) d'exécution du workflow. 
> La construction de Mkdocs prend environ 2 minutes (plus pour les gros dépôts) voire plus (!).
> - La mise à jour des requirements (chaque 24 heures) prend ~30s
> Enfin, vous pouvez exécuter ~1000 build de blog par mois (1500 pour les pro), soit environ 32 build par jour.
> Note : Le cache de pip va normalement accélérer le processus, donc l'action de l'éditeur doit prendre plus de 1min-1min30 que deux pour une petite build.

[^1]: Merci au [site officiel](https://github.com/features/actions)
[^2]: TOC signifie "Table of content", c'est à dire le sommaire. 