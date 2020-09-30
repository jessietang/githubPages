# Vno - Jekyll

[Vno Jekyll](https://github.com/onevcat/vno-jekyll) is a theme for [Jekyll](http://jekyllrb.com). It is a port of my Ghost theme [vno](https://github.com/onevcat/vno), which is originally developed from [Dale Anthony's Uno](https://github.com/daleanthony/uno).

## Live Demo

See [Vno - Jekyll](http://vno.onevcat.com) site and [my blog](http://onevcat.com).

You can also find some instruction as well as other sites using Vno theme in [this page](http://vno.onevcat.com/2016/02/hello-world-vno/).

## Licence

Great thanks to [Dale Anthony](https://github.com/daleanthony) and his [Uno](https://github.com/daleanthony/uno). Vno Jekyll is based on Uno, and contains a lot of modification on page layout, animation, font and some more things I can not remember. Vno Jekyll is followed with Uno and be licensed as [Creative Commons Attribution 4.0 International](http://creativecommons.org/licenses/by/4.0/). See the link for more information.

## start

执行：bundle exec jekyll serve

### 新建一个 md 文件，怎么转换成 html 文件？

index.html or index.md and other HTML, Markdown files ----> Provided that the file has a front matter section, it will be transformed by Jekyll. The same will happen for any .html, .markdown, .md, or .textile file in your site’s root directory or directories not listed above.

front matter section，提供了这个 section,jekyll 就可以把.html, .markdown, .md, or .textile 这些格式的文件转换为.html(在\_site 文件夹下对应的文件)：

```
---
layout: post
title: Blogging Like a Hacker
---
```
