---
share: true
title: Github Actions
---

There is a lot of Github Actions here ! First, if you need information on what is a github action :
> [!cite] Definition
>  GitHub Actions makes it easy to automate all your software workflows, now with world-class CI/CD. Build, test, and deploy your code right from GitHub. Make code reviews, branch management, and issue triaging work the way you want.[^1]

I will explain everything, don't panik. As you can see, here, the github actions (~ the workflow) are used to build Obsidian To Mkdocs (Or Mkdocs Obsidian Publisher) using file in your repo.

> [!info] On push : `mkdocs_build.yml`
> The `.github/workflows/mkdocs_build.yml` file is used to build the mkdocs site.
> It simply run the installations of the requirements and the commands for building github page.
> This workflow will run only for the main or master branch, and if the push includes files from:
> - docs
> - requirements.txt
> - README.md
> - overrides
> - mkdocs.yml

> [!info] Each day : `update_requirements.yml` 
> I created it because the Github Cache needs a fixed version on requirements, but it happens regulary that I update some plugins or update in Material Mkdocs. So, this workflow will **only** change the `requirements.txt` if it founds an update.

> [!info] Activated : `create_index.yml`
> Allow you to quickly create a new "category" / blog listing in your repository, creating a new specified folder with the name of the category.
> To create a new category, follow the steps below:
> 1. Go to the "Actions tab"
> 2. Click on "Index Creation"
> 3. Click on "Run Workflow"
> 4. Fill the form :
>   - **Folder name** : The name of the folder you want to create, it will be the "new category". 
>   - **Parent folder** : The *optional* path of the folder you want to create the new category in. For example, `main_category/draft` will create the `docs/main_category/draft/folder_name` folder.
>   - **Description** : An *optional* category description.
>   - You can also :
>       - **Hide the toc** in the index file.
>       - **Hide the navigation panel** in the index file.
>       - Perform a **dry-run** : It will only show the result of the operation, but will not create the folder and the index file.

You can also create workflow conditional run with the `if` keyword. For example, each merging event will be prepended by `[PUBLISHER]`. You could aussi create a workflow based on pullrequest.

> [!info] Using the if keyword 
> Target the merging event name with : `if: startsWith(github.event.head_commit.message, '[PUBLISHER]')`
> You can use the keyword `if` for steps or entire jobs. 

> [!info] About workflow run
> If you use the workflows (every workflow) on a **private** repository, you needs to know that you have *only* 2000 minutes (3000 with pro account) of workflow run. 
> - Mkdocs Build takes around ~2minutes (more for big repository)
> - Updating requirements (each 24 hours) take ~30s
> Finally, you can run ~1000 blog's build by month (1500 for pro), so it's around 32 build by day.
> Note : The pip cache will normally accelerate the process, so Publisher action must take more than 1min-1min30 than two for little building.

[^1]: Thanks to [official website](https://github.com/features/actions)