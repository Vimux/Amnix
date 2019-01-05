# Amnix [WIP]

**Amnix** is a responsive and configurable [Hugo](https://gohugo.io/) theme.

**[Demo](https://amnix.netlify.com/)**

![Amnix theme screenshot](https://github.com/vimux/amnix/blob/master/images/tn.png)

**Features:**

* Configurable main (home page), list and single layouts [`mainLayout`, `listLayout`, `singleLayout`]
* Featured image
* Configurable main page content sections [`mainSections`]
* Widgets
* MathJax

## Installation

First of all, you will need to [install Hugo](https://gohugo.io/getting-started/quick-start/#step-1-install-hugo) and [create new site](https://gohugo.io/getting-started/quick-start/#step-2-create-a-new-site). After that, you ready to install **Amnix** theme.

There are three different ways you can install **Amnix**:

- **A**. [Git submodule (**Recommended**)](#step-1a-git-submodule-recommended)
- **B**. [Git clone](#step-1b-git-clone)
- **C**. [Download ZIP and manual install](#step-1c-download-zip-and-manual-install)

*For more information read the [Install and Use Themes](https://gohugo.io/themes/installing-and-using-themes/)*

### 1A. Git submodule (Recommended)

In your Hugo site directory, run:

```
git submodule add https://github.com/vimux/amnix themes/amnix
```

Next, edit your `config.toml` configuration file and add parameter:

```
theme = "amnix"
```

*You can [read the GitHub documentation for submodules](https://github.com/blog/2104-working-with-submodules) or those found on [Git's website](https://git-scm.com/book/en/v2/Git-Tools-Submodules) for more information*

### 1B. Git clone

In your Hugo site directory, run:

```
git clone https://github.com/vimux/amnix themes/amnix
```

Next, edit your `config.toml` configuration file and add parameter:

```
theme = "amnix"
```

### 1C. Download ZIP and manual install

[Download ZIP](https://github.com/vimux/amnix/archive/master.zip) and extract to the `themes/amnix` directory

Next, edit your `config.toml` configuration file and add parameter:

```
theme = "amnix"
```

## Configuration

### Config.toml example

```toml
baseurl = "/"
title = "Amnix"
languageCode = "en-us"
paginate = "10" # Number of posts per page
theme = "amnix"
disqusShortname = "" # Enable comments by entering your Disqus shortname
googleAnalytics = "" # Enable Google Analytics by entering your tracking id

[Params]
  description = "Responsive and configurable Hugo theme" # Site description. Used in meta description
  opengraph = true # Enable OpenGraph
  twitterCards = true # Enable Twitter Cards
  homeLayout = "2 columns + sidebar" # Configure home page layout
  listLayout = "2 columns + sidebar" # Configure layout for list pages
  singleLayout = "content + sidebar" # Configure layout for single pages
  mainSections = ["post"] # Set main page sections
  dateFormat = "January 02, 2006" # Change the format of dates
  comments = true # Enable comments for all site pages
  related = true # Enable Related Content (See https://gohugo.io/content-management/related/)
  mathjax = true # Enable MathJax for all site pages
  mathjaxPath = "https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.5/MathJax.js" # Specify MathJax path. Optional
  mathjaxConfig = "TeX-AMS-MML_HTMLorMML" # Specify MathJax config. Optional

[Params.Social] # Site Social block
  email = "example@example.com"
  facebook = "username"
  twitter = "username"
  telegram = "username"
  googleplus = "profileid"
  instagram = "username"
  pinterest = "username"
  vk = "username"
  linkedin = "username"
  github = "username"
  gitlab = "username"
  stackoverflow = "numberid"
  mastodon = "username"
  medium = "username"

[Params.Widgets]
  recent = true # Enable "Recent Posts" widget
  recentNum = 5 # Set number of articles in the "Recent articles" widget
  recentDate = true # Show datetime in the "Recent Posts" widget
  categories = true # Enable "Categories" widget
  tags = true # Enable "Tags" widget
  tagsCounter = true # Enable counter for each tag in the "Tags" widget

[Params.Share] # Post Share block
  facebook = true
  twitter = true
  reddit = true
  telegram = true
  linkedin = true
  googleplus = true
  vk = true
  pocket = true

[Params.Manifest] # Web App Manifest config
  name = "Amnix"
  shortName = "Amnix"
  display = "standalone"
  backgroundColor = "#33333a"
  themeColor = "#5b5b67"
  description = "Responsive and configurable Hugo theme"
  orientation = "portrait"
  startUrl = "/"
  scope = "/"

[outputFormats]
  [outputFormats.MANIFEST] # Add custom MANIFEST output format
    mediaType = "application/json"
    baseName = "manifest"
    isPlainText = true
    notAlternative = true

[outputs]
  home = ["HTML", "RSS", "MANIFEST"] # Include MANIFEST format to home page
```

*For more information about all available configuration settings read [Configure Hugo](https://gohugo.io/getting-started/configuration/)*

### Front Matter example

```yaml
title: "Example article title"
date: 2017-08-21
description: "Example article description"
comments: true # Enable Disqus for specific page
mathjax: true # Enable MathJax for specific page
singleLayout: "content + sidebar" # Change layout for specific page
categories:
  - "Category 1"
  - "Category 2"
tags:
  - "Test"
  - "Another test"
```

*For more information about front matter variables read [Hugo Front Matter](https://gohugo.io/content-management/front-matter)*

### Layouts

**Amnix** comes with several layout options for home, list and single pages.

#### Home & List layouts

Use `homeLayout` parameter in site config to configure home page layout.

Use `listLayout` parameter in site config to configure list pages layout.

Available values: `1 column`, `2 columns`, `3 columns`, `1 column + sidebar`, `2 columns + sidebar`, `3 columns + sidebar`, `1 column + left sidebar`, `2 columns + left sidebar`, `3 columns + left sidebar`

#### Single layouts

Use `singleLayout` parameter in site config to configure single pages layout.

Available values: `content`, `content + sidebar`, `content + left sidebar`

### Footer Social Links

With **Amnix**, you have the option to display links to your social media profiles in the footer. To display them, set up `[Params.Social]` parameters in your site config file.

Available social services: Email, Facebook, Twitter, Telegram, Google+, Instagram, Pinterest, VK, LinkedIn, GitHub, GitLab, Stack Overflow, Mastodon, Medium

### Featured Images

You can add featured images to your content pages. Just put `featured.*` image file in [page bundle](https://gohugo.io/content-management/page-bundles/).

### Web App Manifest

[Web App Manifest](https://developers.google.com/web/fundamentals/web-app-manifest/) is a simple json file with basic site info like name, description, icons, etc. This file tells the browser about your web application and how it should behave when "installed" on the users mobile device or desktop.

To activate Web App Manifest you need to specify `[Params.Manifest]` parameters in your site config file. Add next block in the config file:

```toml
[outputFormats]
  [outputFormats.MANIFEST]
    mediaType = "application/json"
    baseName = "manifest"
    isPlainText = true
    notAlternative = true
```

As a final step, include [custom output format](https://gohugo.io/templates/output-formats) `MANIFEST` for `home` Kind attribute.

```toml
[outputs]
  home = ["HTML", "RSS", "MANIFEST"]
```

*To verify if your manifest file is configured properly and works well, open Chrome DevTools (Press F12 in Chrome) → Application → Manifest*

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md)

## License

**Amnix** is licensed under the [MIT License](https://github.com/vimux/amnix/blob/master/LICENSE).

Social media icons based on:

* [SuperTinyIcons](https://github.com/edent/SuperTinyIcons) (MIT License)
