---
marp: true
theme: default
backgroundColor: #F1F3F3
color: #232F3E
style: |
  section.titleslide h1 {
    color: #ffffff;
  }
  section.titleslide h2 {
    color: #ffffff;
  }
  section.titleslide p {
    color: #ffffff;
  }
  a {
    color: #ff6633;
  }
  video.inslide {
    position: absolute;
    width: 80%;
    height: 80%;
    left: 10%;
  }
  footer {
    position: absolute;
    left: 40%;
    bottom: 30px;
    font-size: 14px;
  }
  img {
    background-color: transparent!important;
  }
header: ''
footer: 'Ceci est du code. A forker depuis [github.com/ojacques/presentations](https://github.com/ojacques/presentations)'

---

<!-- _class: titleslide -->
![bg](title2.jpg)

# La documentation "comme du code"

...ou utiliser la même discipline pour notre documentation que pour notre code

---

# Documentation : La quête de la perfection

# 🏰🦄🤴👸🐴👻⚔🗡🏴‍☠️

---

# 🤯 "Comme du code"

* La documentation est un produit
* Gestion en version avec Git
* Collaboration via les pull requests
* CI/CD: tester et publier automatiquement

---

![bg 95% right:62%](mkdocs1.gif)

# Documentation technique
Avec [MkDocs](https://www.mkdocs.org/) +
[material theme](https://squidfunk.github.io/mkdocs-material/)

---

![bg center 90%](mkdocs2.drawio.png)

---

<!-- _class: titleslide -->
![bg](title2.jpg)

# En pratique

---

![bg right 90%](vscode.jpg)
# Ecrire le texte

Utilisation de [`Markdown`](https://guides.github.com/features/mastering-markdown/)

Avec votre éditeur préféré :

- [VSCode](https://code.visualstudio.com/docs/languages/markdown) 👈
- [IntelliJ](https://www.jetbrains.com/help/idea/markdown.html#navigation)
- Eclipse

---

![bg right 90%](https://github.com/hediet/vscode-drawio/raw/master/docs/drawio-png.gif)
# Ecrire le texte (2)

## Rajouter des extensions

- [markdownlint](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint) (pour la syntaxe)
- [Draw.io](https://marketplace.visualstudio.com/items?itemName=hediet.vscode-drawio) (pour les schémas)
- [PlantUML](https://github.com/qjebbs/vscode-plantuml) (pour les schémas comme du code)
- [Marp](https://marketplace.visualstudio.com/items?itemName=marp-team.marp-vscode) (pour les transparents)

---
# Outillage et frameworks

- [Jekyll](https://jekyllrb.com/) 🤐
- [Hugo](https://gohugo.io/): puissant, léger, rapide 👈
- [Marp](https://marp.app/), [sli.dev](https://sli.dev): transparents / présentations
- [MkDocs](https://www.mkdocs.org/) + [material theme](https://squidfunk.github.io/mkdocs-material/) 👈

---
# CI: Linter - vérifier le markdown

## CLI linter

- [github super-linter](https://github.com/github/super-linter)
- [markdownlint](https://github.com/DavidAnson/markdownlint)
![bg right 80%](linter.png)

## Linter dans l'éditeur

- [VS Code markdownlint extension](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint)

---

# CI: Orthographe

## En ligne de commande

![bg 90% right](spellcheck_code.png)

- [spellcheck-github-actions](https://github.com/rojopolis/spellcheck-github-actions)
- [spellchecker-cli](https://github.com/tbroadley/spellchecker-cli)

## Dans l'éditeur

- [VS Code code-spell-checker extension](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker)

---
# CI: Vérification liens hypertexte

![bg right:62% 95%](markdown-link-check.jpg)

## Liens morts

[markdown-link-check](https://github.com/tcort/markdown-link-check)

---

![bg right:65% 95%](style-vale.jpg)

# CI: Tester

## Style / voix

[Vale](https://github.com/errata-ai/vale)

---
# Publication (CD)

![bg right 95%](github_actions.png)

## Formats

HTML | PDF | DOCX | EPUB | MOBI | ...

## Hébergement web

- [GitHub pages](https://pages.github.com/) 👈
- [GitLab pages](https://docs.gitlab.com/ee/user/project/pages/)
- [Netlify](https://www.netlify.com/)
- Un bucket AWS S3 👈

---
<!-- _class: titleslide -->
![bg](title2.jpg)

# Merci 🙏

<br/>

(Contenu préparé avec Laurent Gil)
