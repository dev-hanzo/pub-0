---
title: Local Folder
---

For the moment, the plugin doesn't support local folder (and any other solution than GitHub). Local folder can be destructive, and I don't want to destroy your Vault on a bad configuration.

So, how to use another solution than GitHub? **You can use a GitHub private repository has a bridge between your Vault and your hosted solution**.

1. Configure the plugin to use GitHub, as described in the [[en/Obsidian/index|configuration]]]
2. Clone the repository on your computer
3. Add your hosted solution has a remote.
4. You can also use a GitHub Action to **send** your changes in your self hosted solution. For example :
   - [Copy via SSH (GitHub Actions)](https://github.com/marketplace/actions/copy-via-ssh)
   - [SCP File Transfer](https://github.com/marketplace/actions/scp-file-transfer)
   - [Mirror to Gitlab and running GitLab CI](https://github.com/marketplace/actions/mirror-to-gitlab-and-run-gitlab-ci)
   - [Mirroring Repository](https://github.com/marketplace/actions/mirroring-repository)

