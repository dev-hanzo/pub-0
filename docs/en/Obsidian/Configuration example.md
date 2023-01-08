---
share: true
title: Configuration example
---

## [Mkdocs Publisher](https://obsidian-publisher.netlify.app)
### Quick installation tutorial
1. Click on [use this template](https://github.com/obsidianPublisher/obsidian-mkdocs-publisher-template/generate)[^1]
2. Use the name of your choice
3. Set and edit the `configuration.yml` in the root of the repository.

### Plugin configuration

1. Folder reception settings : 
    - Reception settings : `YAML frontmatter`
    - Default folder : `docs/notes`
    - Choose your frontmatter key: `category` (you can change it!)
    - Root folder : `docs`
    - [ ] Use the frontmatter "title" to generate the file name (free, personally I use it!)
2. Text conversion
   1. Texts
       - [ ] Strict line breaks
       - [ ] Dataview[^4]
    2. Links 
      - [x] Folder note
      - [x] Internal links
      - [ ] Wikilinks (the template support them by default!) 
3. Embed
   - [x] Image
   - [x] Embedded notes
   - Default folder : `docs/assets/img`
4. Github Workflow
    - **Leave blank the GitHub actions**
    - [x] Auto-clean up 
    - Excluded folder : `docs/assets/js, docs/assets/meta, docs/assets/css, tags.md`[^3]
5. Plugin parameters :
    - Blog link : If you use something else than github pages.
    - Remove a part of the link : `docs/, .md`
    - [ ] Notify all errors (useful for debugging on mobile)

The files (and the images) will be sent on your GitHub repository, in the specified folder. 

[You can also download this file to get quickly the parameters. This file must be in `.obsidian/obsidian-mkdocs-publisher` and you must reload the plugin (or obsidian) to charge the parameters](https://raw.githubusercontent.com/ObsidianPublisher/obsidian-mkdocs-publisher-docs/main/download/data.json)

### Useful informations
#### Links
- [Obsidian Plugin](https://github.com/obsidianPublisher/obsidian-github-publisher)
- [Template](https://github.com/obsidianPublisher/obsidian-mkdocs-publisher-template)
- [Github Discussion](https://github.com/ObsidianPublisher/obsidian-github-publisher/discussions)

#### How to...
- [[en/Getting Started/configuration|Configure the blog]]
- [[en/setup/customization|Customize the blog]]
- [[en/Obsidian/useful plugins.md#Metacopy|Copy links]]
- [[en/Getting Started/upgrading|Update the template]]

#### Support
- [x] Wikilinks (`[[Links]]`)
- [x] File transclusion/embed, both wikilinks and markdown links
- [x] Obsidian callout and custom callout
- [x] Folder notes and their citation
- [x] Custom attributes
- [x] Sharing state and custom folder hierarchy.
- [x] Mobile and desktop
- [x] File mini preview on Hover

#### Limitations

![[../setup/limitations]]

---
## [Digital Garden](https://github.com/TuanManhCao/digital-garden)

1. Folder reception settings : 
    - Reception settings : `Obsidian Path`
    - Default folder : `posts`
2. Workflow : 
    - Leave blank
    - Turn on autoclean
3. Images settings :
    - Transfer embed image on true
    - Transfer embedded notes on false
    - Default folder : `posts/Attachments`

[^1]: You must be connected to copy the template ! You can test locally through clone > https : `git clone https://github.com/ObsidianPublisher/obsidian-mkdocs-publisher-template` or [with downloading the ZIP](https://github.com/ObsidianPublisher/obsidian-mkdocs-publisher-template/archive/refs/heads/main.zip)
[^2]: You need to be connected to generate it.
[^3]: Normally, only file supported by obsidian are deleted, but some image exists only on the blog (for logo, for example). To prevent bad surprise, exclude these folder here.
[^4]: You are free to convert or not the **simple** dataview bloc in Markdown. If this option is disabled, the bloc will be deleted complety in the converted file. 
