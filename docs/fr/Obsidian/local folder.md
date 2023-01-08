---
title: Dossiers locaux
---

Pour le moment, le module ne permet pas d'utiliser un dossier local (et aucun moyen d'hébergement autre que GitHub). Le dossier local peut être destructif, et je ne veux pas détruire votre Vault sur une configuration incorrecte.

Donc, comment utiliser un autre moyen d'hébergement? **Vous pouvez utiliser un dépôt privé GitHub qui relie votre Vault à votre solution d'hébergement**.

1. Configurez le module pour utiliser GitHub, comme décrit dans la [[fr/Obsidian/index|configuration]]]
2. Clonnez le dépôt sur votre ordinateur
3. Ajouter votre solution d'hébergement comme un dépôt distant.
4. Vous pouvez aussi utiliser une action GitHub pour **envoyer** vos changement dans votre solution d'hébergement. Par exemple :
    - [Copy via SSH (GitHub Actions)](https://github.com/marketplace/actions/copy-via-ssh)
   - [SCP File Transfer](https://github.com/marketplace/actions/scp-file-transfer)
   - [Mirror to Gitlab and running GitLab CI](https://github.com/marketplace/actions/mirror-to-gitlab-and-run-gitlab-ci)
   - [Mirroring Repository](https://github.com/marketplace/actions/mirroring-repository)
