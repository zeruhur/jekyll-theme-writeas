# jekyll-theme-writeas
A Write.as minimal theme for Jekyll

<div align="center">

[![Live Preview](https://user-images.githubusercontent.com/39684348/109401128-da174200-791a-11eb-9b69-eb083f4a2522.png)](https://ethanmcbloxxer.github.io/jekyll-theme-writeas/)  
*click the image to preview the theme in your browser*

</div>

## Installing
There isn't much detail in this guide , it assumes the user has expirence with Jekyll and setting up themes. Please see [JekyllRB.com](https://jekyllrb.com/docs/posts/) or gain some experience somehow.

Add this to your site's `_config.yml`:
```yml
permalink: /:title/
paginate: 10 # how many posts on a page
remote_theme: EthanMcBloxxer/jekyll-theme-writeas@main
plugins:
  - jekyll-remote-theme
  - jekyll-paginate
```
and to your site's `index.html` (not `index.md`):
```yml
---
layout: home
---
```

## Posting
Add `YEAR-MONTH-DAY-Title.md`-formatted posts into a directory called `_posts`. See examples in the `demo` branch.

### Custom Front Matter
To pin a post, please add this to your post's front matter:
```yml
---
pinned: true
hidden: true # this will remove it from pagination
---
```

### Pages
There isn't a primary `page.html` layout file for pages. Just make a file in `/` and give it `layout: post`. That should hopefully suffice.

## Customization
Inside your site's `_config.yml`, the following keys are supported:
```yml
# please replace the part after the colon (:) with what you want to be displayed

## MAIN ##
title: "EthanMcBloxxer" # title of blog or your name
subtitle: "Creator of Writeas.Jekyll" # subtitle of blog or your position / minbio
links:
  about: /about/
  contact: mailto:EthanMcBloxxer@pm.me
  rss: /feed.xml
credit: true # show a footer "published with jekyll-theme-writeas" (only on posts)

## FONTS ##
serif: true # use a serif font (Lora) instead of sans-serif (Open Sans); "monospace" is also supported

## PAGINATE ##
paginate_path: "/page/:num/" # page 2 would be served at /page/2/
older_text: false # text to be displayed for older posts nav
newer_text: false # text to be displayed for newer posts nav

## COLORS ##
background: "#f5f5f5" # page background color in HEX
text: "#111" # text color in HEX
accent: "#777" # text accent (subtitles, read more, etc) in HEX
link: "#9f9fff" # link color in HEX
code: "#586e75" # default code color in HEX
```

you can add the setup code shown at the beginning above or below all of those keys.

### Dark Mode
I've created a good set of color keys to use with your `_config.yml` if you want your site in dark:
```yml
background: "#202325"
text: "#dadad9"
accent: "#dadad9"
link: "#139ee0"
code: "#cccccc"
```

## RSS
If you need an RSS Feed, then you can make a new file called `feed.xml` (or whatever you want) with the following content:
```yml
---
layout: rss
title: RSS Feed Title
limit: 20 # how many posts to limit the feed to
---
```
then, if you'd like, you can reflect that in your `links` key inside of `_config.yml`.
