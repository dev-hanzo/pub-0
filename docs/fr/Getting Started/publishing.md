---
title: Publication
---

## Déploiement & publication

Vous pouvez publier votre site via :
- [Netlify](https://www.netlify.com/)
- [Github Pages](https://pages.github.com/)

## Par GitHub Pages

Le blog sera publié via [GitHub Page](https://pages.github.com/) en utilisant la branche `gh-page`. 

> [!bug] J'ai le README à la place de mes fichiers !
> Vérifier la branche `gh-pages` et l'activer si nécessaire dans `Settings` → `Pages`
> ![image](https://user-images.githubusercontent.com/30244939/166161220-973cee87-75eb-4b9f-b521-1c67d273def7.png)

> [!bug] Le workflow ne s'exécute pas !
> - Vérifiez l'exécution et l'erreur dans `Actions`. 
> - Vérifiez si les actions ont les bons accès en écriture et en lecture dans `Settings → Actions → General → workflow permission` ![image](https://user-images.githubusercontent.com/30244939/166161294-0f4f70c2-fda5-4465-89b0-d6b1b5e6995d.png)
>> [!Avertissement] En cas de problème de worfklow
>> Dans le [problème #4](https://github.com/obsidianPublisher/obsidian-github-publisher/issues/4), nous avons découvert que parfois, les actions Github refusent de s'exécuter sans raison. Si cela vous arrive, veuillez contacter le support Github !

## Par Netlify

Netlify est un service qui permet de publier votre blog gratuitement sur un site web, et la construction du blog (*build*) sera beaucoup plus rapide que via GitHub.

Pour déployer votre blog, vous pouvez cliquer ici : [![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/ObsidianPublisher/obsidian-mkdocs-publisher-template)

Alternativement : 
- Créer un compte sur Netlify.app
- Ajouter un nouveau site en utilisant un dépôt déjà existant. 
    Pour la configuration, vous pouvez utiliser :
    - Laisser blanc pour le `base directory`
    - <u>Build command</u> : `mkdocs build`
    - <u>Publish directory</u> : `site`
- Prendre le fichier `runtime.txt` et le rajouter à la racine de votre dépôt, ou créer une nouvelle variable d'environnement nommée `PYTHON_VERSION` fixée à `3.8`.

Afin de gagner du temps sur la build et économiser votre bande passante/temps de déploiement, vous devez désactiver la prévisualisation du blog à chaque push. 
Pour cela, rendez-vous dans le menu `settings` -> `build & deploy` -> `deploy-previews`
![picture 1](https://i.imgur.com/DNS0DdX.png)  


> [!note]
> Il peut être possible que vous ayez besoin de supprimer la branch `gh-pages` pour supprimer l'ancienne page GitHub Pages.

> [!info] Avantages/inconvénients
>> [!info] Avantages
>> - Plus rapide que GitHub Pages (1min VS 3min)
>> - Gratuit
>> - Pas besoin de s'inquiéter du temps des workflow dans les dépôt privés.
>> - Meilleur liens et customisation de ses derniers.
>
>> [!info] Inconvénients
>> - Vous avez besoin d'un compte Netlify pour déployer votre blog.
>> - Limité par la bande passante à 100GB pour tous les sites
>> - Limités à 300minutes/build par mois.


[^1]: Vous pouvez trouver le lien dans `Settings > Pages`
