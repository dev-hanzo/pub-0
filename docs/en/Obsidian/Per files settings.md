---
title: Per files settings
---

## Changing repository
:sparkles: It is now possible to set a repository directly in the frontmatter with the `repo` key.

> [!warning]
> - Your GitHub token must work for this repository
> - Global function (sharing all new note, all shared notes...) won't send file to this "per-file" repository : only the command `share one note` will work but the **cleaning** will be done too! (see [auto clean up for more information](#auto-clean-up)). You can disable the cleaning with the `clean: false` key in the frontmatter.
> - The key works in this order : `username/repo/branch`, `username/repo` and `repo`. You can also use a yaml object like that :
>  ```yaml
>  repo:
>    owner: username
>    repo: repo
>    branch: branch
>  ```
> Globally, if you share only one file, all function will be on the per-file repository instead of the global one. 
> Also, the settings will be the **same** as the global one, except for repo : image, folder, etc...

:sparkles: You can also set multiple repositories in the frontmatter with the `multipleRepo` key. It works like the `repo` key, but you can set multiple repositories, in a list!
> [!example] Example
> ```yaml
> multipleRepo:
>  - owner: username
>    repo: repo
>    branch: branch
>  - owner: username
>    repo: repo
>    branch: branch
> ```
> You can also use a list of string.

> [!note] 
> - By default, autoclean is set to `false`. You can add the `autoclean` key in the frontmatter to change this behavior : you can configure the autoclean per repos!
> - You can also use this key with only one repo.

## Frontmatter keys explanation

Some settings can be overridden based on your frontmatter key (of the file send):
1. For links conversion, using the `links` key, you can create an yaml object with:
	- `mdlinks` : to force converting to markdown links.
	- `convert` or `links` : to remove the links to just keeps the string (alt text or filename).
    - `internals` : Convert internal links to their counterpart in the website (in relative path). Disabled, links will be keep as is.
    - `nonShared` : Same as above, but for links pointing to unshared files. Disabled, links will be transformed to keep the filename.
	Note that you can use `links: false` and `mdlinks: true` outside the yaml object if you want to just use one option.
2. Embed settings, using the `embed` key :
	- `send:false` avoid the sending of the embedded files (not attachment!)
	- `remove: true` to remove any mention of these file
	As before, you can use one key settings using `embed` (for sending) and `removeEmbed` (for citation removing)
3. `Attachment` : allow per file settings for attachment (image, pdf, sound, video... Any attachment supported by Obsidian)
	- `send: false` to avoiding sending the files
	- `folder` to change the default folder. Beware that changing this settings can have strange effect with autocleaning!
	You can, again, use a one key settings using `attachmentLinks` for the folder and `attachment: false` to avoiding sending.
4. `dataview` to overrides dataview settings.
5. `hardbreak` for markdown hard break.
6. `baselink` : to change the baselink for the copy links function.


## Quick references
### Using yaml object

```yaml
links:
  mdlinks: boolean #convert to markdownlinks 
  convert: boolean #transform to simple string with keeping alt text or file name/ title (it removes the [[]] or []())
embed:
  send: boolean #prevent sending embed
  remove: boolean #remove embed citation completely (replace to empty string the ![[]] or ![]())
attachment: 
  send: boolean #prevent sending attachment
  folder: string #change default folder for attachment
dataview: boolean #force/prevent dataview queries conversion
hardbreak: boolean #same but for hardbreak
repo: 
  branch: string #change default branch 
  repo: string #change default repository
  owner: string #change default owner (it's your github Username)
autoclean: boolean #disable auto cleaning
baselink: string #change base link for copylink settings
```

For multiple Repo :
```yaml
links:
  mdlinks: boolean #convert to markdownlinks 
  convert: boolean #transform to simple string with keeping alt text or file name/ title (it removes the [[]] or []())
embed:
  send: boolean #prevent sending embed
  remove: boolean #remove embed citation completely (replace to empty string the ![[]] or ![]())
attachment: 
  send: boolean #prevent sending attachment
  folder: string #change default folder for attachment
dataview: boolean #force/prevent dataview queries conversion
hardbreak: boolean #same but for hardbreak
baselink: string #change base link for copylink settings
multipleRepo: 
  - repo:
      branch: string #change default branch 
      repo: string #change default repository
      owner: string #change default owner (it's your github Username)
      autoclean: boolean #enable auto cleaning
  - repo:
      branch: string #change default branch 
      repo: string #change default repository
      owner: string #change default owner (it's your github Username)
      autoclean: boolean #enable auto cleaning
```

### Using simple name

```yaml
mdlinks: boolean #convert to markdown links
links: boolean #remove [[]] or []() and keep just alt text or filename/title
removeEmbed: boolean #remove totally the citation of an embed notes (replace to empty string the ![[]] or ![]())
attachmentLinks: string #ovverride default folder for attachments
attachment: boolean #prevent sending attachment
dataview: boolean
hardbreak: boolean
repo: string #owner/repo/branch or owner/repo or repo
autoclean: boolean #disable auto cleaning
baselink: string #change base link for copylink settings
```

For multiple Repo :
```yaml
mdlinks: boolean #convert to markdown links
links: boolean #remove [[]] or []() and keep just alt text or filename/title
removeEmbed: boolean #remove totally the citation of an embed notes (replace to empty string the ![[]] or ![]())
attachmentLinks: string #ovverride default folder for attachments
attachment: boolean #prevent sending attachment
dataview: boolean
hardbreak: boolean
baselink: string #change base link for copylink settings
multipleRepo: list of string 
    - owner/repo/branch/autoclean or owner/repo or repo
    - owner/repo/branch/autoclean or owner/repo or repo
```

Default value is derivative from your settings :  (`settings.keys` refer to your settings)

```yaml
links:
  mdlinks: settings.wikilinks
  convert: true
embed: 
  send: settings.embed
  remove: false
attachment:
  send: settings.attachment
  folder: settings.default_folder_image || settings.default_folder || filepath
dataview: settings.dataview
hardbreak: settings.hardbreak
repo: #same for multipleRepo
  branch: settings.branch
  repo: settings.repo
  owner: settings.owner
autoclean: settings.auto_clean
baselink: string #change base link for copylink settings
```
