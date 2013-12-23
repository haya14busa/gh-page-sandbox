---
layout: default
title: Happy Vimming!
---

GitHub Pages for Project
=====

[http://haya14busa.github.io/gh-page-sandbox/](http://haya14busa.github.io/gh-page-sandbox/)

- [GitHub Pages](http://pages.github.com/#project_pages)
- [GitHub Help](https://help.github.com/categories/20/articles)

### Generate a Site
1. Press repository `Setting` buttun
2. Press the Automatic Page Generator button.
3. Happy!
```
\("`v")/
```

## Scrach
### 1.Create `gh-pages` branch

```
git checkout --orphan gh-pages
rm .git/index
git clean -fdx
```
### 2. `echo 'Happy Vimming!' > index.html`

### 3. Add & Commit & Push!
```
git add index.html
git commit -m 'Happy Vimming!'
git push -u origin gh-pages
```

URL
:   `http://{username}.github.com/{repository-name}`

Jekyll
-----
- [Jekyll • Simple, blog-aware, static sites](http://jekyllrb.com/)
    - Document: [Welcome](http://jekyllrb.com/docs/home/)
- [Using Jekyll with Pages · GitHub Help](https://help.github.com/articles/using-jekyll-with-pages)
- [Jekyllいつやるの？ジキやルの？今でしょ！](http://melborne.github.io/2013/05/20/now-the-time-to-start-jekyll/)


### Plugin
- [Plugins](http://jekyllrb.com/docs/plugins/)

> #### Plugins on GitHub Pages
> GitHub Pages is powered by Jekyll, however all Pages sites are generated using the --safe option to disable custom plugins for security reasons. Unfortunately, this means your plugins won’t work if you’re deploying to GitHub Pages.
> -- <cite>[Plugins](http://jekyllrb.com/docs/plugins/)</cite>

### Octopress
- [Octopress](http://octopress.org/)
- [imathis/octopress](https://github.com/imathis/octopress)
- [Big Sky :: githubとjekyllとoctopressで作る簡単でモダンなブログ](http://mattn.kaoriya.net/software/lang/ruby/20111017205717.htm)

GitHub Pagesでは通常Jekyllのプラグインは使用できないが、OctopressでローカルにJekyllを動かす->Pushすればプラグインが使える(おそらく)

### Jekyll-bootstrap
- [The Quickest Way to Blog on GitHub Pages. | ruhoh universal static blog generator](http://jekyllbootstrap.com/)
- [jekyll-bootstrap/](https://github.com/plusjade/jekyll-bootstrap/)


GitHub PagesでGenerateした場合(Timemachine theme)
-----

cloneしたりごにょごにょ

### Convert Markdown

Shell

```
mkdir _layouts/
git mv index.html _layouts/default.html
vim default.html
```

いい感じにする

\_layouts/default.html

~~~
{\% if page.title %}\{\{ page.title }}{\% endif %}
\{\{content}}
etc ...
~~~
スラッシュ(\\)無視で(反応してしまってダメだった)

\_config.yml

```
markdown: rdiscount
```
- [RDiscount | Markdown for Ruby | DaFoster](http://dafoster.net/projects/rdiscount/)

### Write Markdown
index.md
```
---
layout: default
title: Happy Vimming!
---
\("`v")/
```


### Add Gemfile
Gemfile

```
source 'https://rubygems.org'
gem 'github-pages'
```

### Install
```
bundle install
```

### Localでチェック
```
bundle exec jekyll serve -w
```
`-w`でwatchして自動ビルド

いい感じになったらgh-pagesにpush

```
git push -u origin gh-pages
```


Sub directory
-----

[subディレクトリのテスト](./sub/)

\_config.yml

```
markdown: rdiscount
base-url: /gh-page-sandbox/
```

Shell

```
bundle exec jekyll serve -w -b '/gh-page-sandbox/'
```

これでローカルでもCSS,JSがちゃんと効く(おそらく)
URL: http://0.0.0.0:4000/gh-page-sandbox/
