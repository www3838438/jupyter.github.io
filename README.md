# Jupyter's main website

[![Build Status](https://travis-ci.org/jupyter/jupyter.github.io.svg?branch=master)](https://travis-ci.org/jupyter/jupyter.github.io)

This is the source to [Jupyter.org](http://jupyter.org/).

# Build instructions

The site is built using GitHub Pages Jekyll, see [Jekyll
website](http://jekyllrb.com/) for customizing the build process, and detail on how
what where.

# Quick local testing

```
gem install bundler
bundle install
```

cd into the root of this directory,

```
bundle exec jekyll serve --baseurl ''
```

Open your browser to localhost:4000.

Edit the various parts and reload at will.

Enjoy.

# What is where

Most pages are located at the place where their URL is, nothing fancy.  Headers
and footer are in `_includes/head.html`, `_includes/header.html`,
`_includes/footer.html`.

The **navbar** is in `_data/nav.yml` and looks like that:

```
head:
    - Home
    - title: Install
      url: https://jupyter.readthedocs.io/en/latest/install.html
    - About
    - title: Documentation
      url: https://jupyter.readthedocs.io/en/latest/install.html
    - title: Blog
      url: https://blog.jupyter.org
    - Donate
```

which means, insert in order the following links into the navbar:

    - Link to `Home` page, guess the url by yourself. 
    - link to `Install` page, the url is...
    - Link to `About`, guess the url by yourself, 
    -  ... etc.

The navbar will automatically target `_blank` pages where the url is explicit,
and mark the correct link as the "current" one.

# How do I create a new page?

Create `my_page.html` (will have url `https://jupyter.org/my_page.html`)
or `my_page/index.html` (will have url `https://jupyter.org/my_page/`), start with the following:

```
---
layout: default
title: My Page
---

write some html here (consider you are already inside `<body></body>`)
```

You cannot do it yet with .md file, but you will be able soon.

Add commit (and don't forget to add to `_data/nav.yml`).

# Continuous integration testing on Travis

Travis will run and test:

- jekyll build
- html-proofer
- csslint

