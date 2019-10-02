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

*First of all, you will need to [install Hugo](https://gohugo.io/getting-started/quick-start/#step-1-install-hugo) and [create new site](https://gohugo.io/getting-started/quick-start/#step-2-create-a-new-site). Also, you have git installed on your machine and you are familiar with basic git usage. After that, you ready to install **Amnix**.*

There are three different ways you can install **Amnix**. Choose one of the installation methods listed below and follow the instructions.

- **A**. [Git clone](#option-a-git-clone)
- **B**. [Git submodule](#option-b-git-submodule)
- **C**. [Download ZIP and manual install](#option-c-download-zip-and-manual-install)

*For more information read the "[Install and Use Themes](https://gohugo.io/themes/installing-and-using-themes/)"*.

### Option A. Git clone

In your Hugo site directory, run:

```
git clone https://github.com/vimux/amnix themes/amnix
```

Next, edit your `config.toml` configuration file and add parameter:

```
theme = "amnix"
```

### Option B. Git submodule

In your Hugo site directory, run:

```
git submodule add https://github.com/vimux/amnix themes/amnix
```

Next, edit your `config.toml` configuration file and add parameter:

```
theme = "amnix"
```

*You can [read the GitHub documentation for submodules](https://github.com/blog/2104-working-with-submodules) or those found on [Git's website](https://git-scm.com/book/en/v2/Git-Tools-Submodules) for more information*

### Option C. Download ZIP and manual install

**[Download ZIP](https://github.com/vimux/amnix/archive/master.zip)** and extract to the `themes/amnix`

Next, edit your `config.toml` configuration file and add parameter:

```
theme = "amnix"
```

***

You can run your site in Hugo server mode:

```
hugo server
```

Now you can go to [localhost:1313](http://localhost:1313) webpage and the Amnix theme should be visible.

After you make sure that **Amnix** works, you may start customizing the theme if it's needed.

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
  customCSS = ["css/custom.css"] # Include custom CSS files
  comments = true # Enable comments for all site pages
  related = true # Enable Related Content (See https://gohugo.io/content-management/related/)
  mathjax = true # Enable MathJax for all site pages
  mathjaxPath = "https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.6/MathJax.js" # Specify MathJax path. Optional
  mathjaxConfig = "TeX-AMS-MML_HTMLorMML" # Specify MathJax config. Optional

[Params.Featured]
  previewOnly = false # Show only preview featured image

[Params.Social] # Site Social block
  email = "example@example.com"
  facebook = "username"
  twitter = "username"
  telegram = "username"
  instagram = "username"
  pinterest = "username"
  vk = "username"
  linkedin = "username"
  github = "username"
  gitlab = "username"
  stackoverflow = "numberid"
  mastodon = "https://some.instance/@username"
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
# Common-Defined params
title: "Example article title"
date: 2017-08-21
description: "Example article description"
categories:
  - "Category 1"
  - "Category 2"
tags:
  - "Test"
  - "Another test"

# Theme-Defined params
singleLayout: "content + sidebar" # Change layout for specific single page
comments: true # Enable/disable Disqus for specific page
mathjax: true # Enable/disable MathJax for specific page
related: true # Enable/disable Related content for specific page
featured:
  url: image.jpg # relative path of the image
  alt: A scale model of the Eiffel tower # alternate text for the image
  caption: Eiffel tower model # image caption
  credit: Unknown author # image credit
  previewOnly: false # show only preview image (true/false)
```

*For more information about front matter variables read [Hugo Front Matter](https://gohugo.io/content-management/front-matter)*

### Configuration options

#### Layouts

**Amnix** comes with several layout options for home, list and single pages.

##### Home & List layouts

Use `homeLayout` parameter in site config to configure home page layout.

Use `listLayout` parameter in site config to configure list pages layout.

Available values: `1 column`, `2 columns`, `3 columns`, `1 column + sidebar`, `2 columns + sidebar`, `3 columns + sidebar`, `1 column + left sidebar`, `2 columns + left sidebar`, `3 columns + left sidebar`

##### Single layouts

Use `singleLayout` parameter in site config to configure single pages layout.

Available values: `content`, `content + sidebar`, `content + left sidebar`

#### Custom CSS

If you want to include custom CSS files, you need to assign an array of references in site config file (`config.toml` by default) like following:

```toml
[Params]
  customCSS = ["css/custom.css"]
```

Of course, you can reference as many CSS files as you want. Their paths need to be relative to the `static` folder of your Hugo site:

```toml
[Params]
  customCSS = ["css/custom.css", "css/another.css"]
```

All these CSS files will be added through the `head.html` partial after the built-in CSS file.

#### Footer Social Links

With **Amnix**, you have the option to display links to your social media profiles in the footer. To display them, set up `[Params.Social]` parameters in your site config file.

Available social services: Email, Facebook, Twitter, Telegram, Instagram, Pinterest, VK, LinkedIn, GitHub, GitLab, Stack Overflow, Mastodon, Medium

#### Featured Image

There are two main different ways to add a featured image for a page.

**Option 1.** Put `featured.*` or `thumbnail.*` image file in the
[page bundle](https://gohugo.io/content-management/page-bundles/).

**Option 2.** Put any image in the page bundle & specify `featured` param in the page's front matter.

You may put any image in the page bundle and specify `featured` param in the page's front matter:

```yaml
featured: image.jpg
```

Or you can add some additional params like `alt`, `caption`, `credit` and `previewOnly`:

```yaml
featured:
  url: image.jpg
  alt: A scale model of the Eiffel tower standing on a map
  caption: Eiffel tower model
  credit: Unknown author
  previewOnly: false
```

**Note**: `caption` and `credit` appear only on single pages, not summaries.

#### Web App Manifest

[Web App Manifest](https://developers.google.com/web/fundamentals/web-app-manifest/) is a simple json file with basic site info like name, description, icons, etc. This file tells the browser about your web application and how it should behave when "installed" (PWA) on the users mobile device or desktop.

To activate Web App Manifest you need to define `MANIFEST` custom output format & specify `[Params.Manifest]` parameters in your site config file.

First of all, you should define `MANIFEST` custom output format:

```toml
[outputFormats]
  [outputFormats.MANIFEST]
    mediaType = "application/json"
    baseName = "manifest"
    isPlainText = true
    notAlternative = true
```

Then, include `MANIFEST` output format for `home` Kind attribute:

```toml
[outputs]
  home = ["HTML", "RSS", "MANIFEST"]
```

After that, you can specify `[Params.Manifest]` parameters.

*To verify that your manifest file is configured properly and works well, run Hugo server and open Chrome DevTools (Press F12 in Chrome) → Application → Manifest*

## Contributing

See [CONTRIBUTING.md](https://github.com/vimux/amnix/blob/master/CONTRIBUTING.md)

## License

**Amnix** is licensed under the [MIT License](https://github.com/vimux/amnix/blob/master/LICENSE).

* Social media icons based on [SuperTinyIcons](https://github.com/edent/SuperTinyIcons) (MIT License)
* CSS Reset based on [Bootstrap Reboot](https://github.com/twbs/bootstrap/blob/master/dist/css/bootstrap-reboot.css) (MIT License)
