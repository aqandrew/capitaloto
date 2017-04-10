# Capital Region Otolaryngology

Welcome to the Github code repository for the overhaul of <http://capitaloto.com>!

## How does this work?

This website uses a static website generator called [Jekyll][jekyll]. It's a Ruby gem (software package) which builds webpages from partial HTML files, and blog posts using the Markdown markup language.

This way, you won't have to physically change the footer in every single page if hours change, for example.

## Development

1. [Build and serve](#build-serve) the website.
2. [Write an announcement post](#write-post) or make other changes. Jekyll will rebuild the site in the `_site` folder whenever you save changes to any file (besides `_config.yml`). Any changes directly made to `_site` files are overwritten whenever the site is rebuilt.
3. Once you've made the changes you want, upload the contents of `_site` using the appropriate FTP credentials.

<a name="build-serve"></a>
Already have Ruby, Bundler, and Jekyll installed? Build the site using this command:

```shell
$ bundle exec jekyll serve
```

If you're drafting a post, preview it by running with the `--drafts` flag.

Then navigate to `localhost:4000` in your browser.

To build without serving:

```shell
$ bundle exec jekyll build
```

### Writing an announcement

To begin writing an announcement post, place a new Markdown file in the `_drafts` folder. The title can be anything you want.

#### What's Markdown?

[Markdown][markdown] an abstraction of HTML that provides shortcuts to create inline styles like headings, links, *italicized* and **bold text**, and even images from urls&mdash;just by using punctuation.

 [This Markdown cheat sheet][markdown-cheatsheet] provides a quick and easy reference for most of the styling and elements you'll need.

Each Markdown file in Jekyll requires [Front Matter][front-matter] before all other content. This information, wrapped in triple-dashes, defines keys and values that Jekyll references to build HTML pages, such as a title or primary image URL.

```markdown
---
layout: post
title: CapitalOto Welcomes Jane Doe, PhD
---
```

#### Post templates

You can copy/paste the format of the post from any of the template posts already in `_drafts`&mdash;these include front matter with keys already defined, ready to be populated.

When you're ready to publish the post, move the file to `_posts` with a filename of the format `YYYY-MM-DD-your-title.md`.

## Setup

1. [Install Ruby](#install-ruby).
2. [Install Bundler and Jekyll gems](#install-bundler-and-jekyll-gems).
3. [Install other necessary gems](#install-other-necessary-gems).

### Install Ruby

To make changes to the site on Windows...

#### Windows

You need to [install Ruby][ruby-installer] and its [DevKit][ruby-devkit]. The latter provides a command line interface for actions like installing gems, or building the site locally.

When you've downloaded the DevKit, run these commands in Command Prompt:

```
> chdir C:\path\to\DevKit
> ruby dk.rb init
> ruby dk.rb install
```

*Note: you don't need to type the '>' symbol.*

##### macOS

Ruby has been included with every OS X release since Mountain Lion. The big cats (Mountain Lion, Lion, Snow Leopard) come with Ruby 1.8.7, while later versions (El Capitan, Yosemite, Mavericks, Sierra) come with Ruby 2.0.

You can get the newest version of Ruby using [Homebrew][homebrew]:

```shell
$ brew install ruby
```

##### Linux

The `ruby-full` apt package provides Ruby 1.9.3 on Debian and Ubuntu.

```shell
$ sudo apt-get install ruby-full
```

---

#### Install Bundler and Jekyll gems

```shell
$ bundle install bundler jekyll
```

#### Install other necessary gems

In the directory where this repository has been downloaded:

```shell
$ bundle install
```

[![Start Video](https://github.com/Phlow/feeling-responsive/blob/gh-pages/images/video-feeling-responsive-1280x720.jpg)](https://www.youtube.com/embed/3b5zCFSmVvU)

## About the Theme: *Feeling Responsive*

Do you want to get to know *Feeling Responsive*? Then check it out first and have a look on [its home][feeling-responsive]!

Many of its features are explained in its [documentation][feeling-responsive-documentation].

[jekyll]: https://jekyllrb.com/
[markdown]: https://daringfireball.net/projects/markdown/syntax
[markdown-cheatsheet]: https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet
[front-matter]: https://jekyllrb.com/docs/frontmatter/
[ruby-installer]: https://rubyinstaller.org/
[ruby-devkit]: http://rubyinstaller.org/downloads/
[homebrew]: https://brew.sh/
[feeling-responsive]: http://phlow.github.io/feeling-responsive/
[feeling-responsive-documentation]: http://phlow.github.io/feeling-responsive/documentation/

[andrew-aquino]: https://dawneraq.github.io
