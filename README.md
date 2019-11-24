# Amnix [WIP]

**Amnix** is a responsive and configurable [Hugo](https://gohugo.io/) theme.

**[Demo](https://amnix.netlify.com/)**

![Amnix theme screenshot](https://github.com/vimux/amnix/blob/master/images/tn.png)

**Features:**

* Configurable home, list and single layouts
* Featured image
* Configurable main page content sections [`mainSections`]
* Widgets
* MathJax

## Table of Contents

- [Installation](#installation)
  - [Option A. Git clone](#option-a-git-clone)
  - [Option B. Git submodule](#option-b-git-submodule)
  - [Option C. Download ZIP and manual install](#option-c-download-zip-and-manual-install)
- [Configuration examples](#Configuration-examples)
  - [Config.toml example](#configtoml-example)
  - [Front Matter example](#front-matter-example)
- [Configuration options](#configuration-options)
  - [Columns](#columns)
  - [Sidebar](#sidebar)
    - [Sidebar position](#sidebar-position)
  - [Custom CSS](#custom-css)
  - [Custom JS](#custom-js)
  - [Featured image](#featured-image)
  - [Meta Fields](#meta-fields)
  - [Menus](#menus)
  - [Footer Social Links](#footer-social-links)
  - [Web App Manifest](#web-app-manifest)
- [Contributing](#contributing)
- [License](#license)

## Installation

*First of all, you will need to [install Hugo](https://gohugo.io/getting-started/quick-start/#step-1-install-hugo) and
[create a new site](https://gohugo.io/getting-started/quick-start/#step-2-create-a-new-site). Also, you have git
installed on your machine and you are familiar with basic git usage. After that, you ready to install **Amnix**.*

There are three different ways you can install **Amnix**. Choose one of the installation methods listed below and follow
the instructions.

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

*You can [read the GitHub documentation for submodules](https://github.com/blog/2104-working-with-submodules) or those
found on [Git's website](https://git-scm.com/book/en/v2/Git-Tools-Submodules) for more information*

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

## Configuration examples

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
  columns = 2 # Set the number of content cards columns. Possible values: 1, 2, 3
  mainSections = ["post"] # Set main page sections
  dateFormat = "January 02, 2006" # Change the format of dates
  customCSS = ["css/custom.css"] # Include custom CSS files
  customJS = ["js/custom.js"] # Include custom JS files
  comments = true # Enable comments for all site pages
  related = true # Enable Related Content (See https://gohugo.io/content-management/related/)
  mathjax = true # Enable MathJax for all site pages
  mathjaxPath = "https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.6/MathJax.js" # Specify MathJax path. Optional
  mathjaxConfig = "TeX-AMS-MML_HTMLorMML" # Specify MathJax config. Optional

[Params.Featured]
  previewOnly = false # Show only preview featured image

[Params.Sidebar]
  widgets = ["recent", "categories", "tags"] # Enable sidebar widgets in given order
  position = "right" # Change sidebar position for all site pages: "right", "left" or false
  positionHome = "right" # Change sidebar position for home page
  positionList = "right" # Change sidebar position for list pages
  positionSingle = "right" # Change sidebar position for single pages

[Params.Widgets]
  recentNum = 5 # Set number of articles in the "Recent articles" widget
  recentDate = true # Show datetime in the "Recent Posts" widget
  tagsCounter = true # Enable counter for each tag in the "Tags" widget

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
  startUrl = "/"
  backgroundColor = "#33333a"
  themeColor = "#5b5b67"
  description = "Responsive and configurable Hugo theme"
  orientation = "portrait"
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

*For more information about all available configuration settings read
[Configure Hugo](https://gohugo.io/getting-started/configuration/)*

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
comments: true # Enable/disable Disqus for specific page
mathjax: true # Enable/disable MathJax for specific page
related: true # Enable/disable Related content for specific page
featured:
  url: image.jpg # relative path of the image
  alt: A scale model of the Eiffel tower # alternate text for the image
  caption: Eiffel tower model # image caption
  credit: Unknown author # image credit
  previewOnly: false # show only preview image (true/false)
meta:
  - date
sidebar:
  position: left # Change sidebar position per page: "right", "left" or false
  widgets:
    - recent
    - tags
```

*For more information about front matter variables read
[Hugo Front Matter](https://gohugo.io/content-management/front-matter)*

## Configuration options

### Columns

Amnix ships with configurable column layout for home & list pages. To create multiple column layout change
`Params.columns` key to preferable value (from 1 to 3):

```toml
[Params]
  columns = 2
```

You can also change this option for specific list page in the front matter:

```yaml
columns: 2
```

Please note that the layout will display multiple columns only if it's possible by screen size.

### Sidebar

The sidebar is an area to the side of a page that acts as a "container" for widgets. **Amnix** comes with a configurable
sidebar that can be customized using parameters.

To create a sidebar block with widgets, use the `widgets` config key with a list of widget names as value under
`[Params.sidebar]` section of the config file:

```toml
[Params.sidebar]
  widgets = ["recent", "categories", "tags"]
```

Widgets can be also configured per page through front matter:

```yaml
sidebar:
  widgets:
    - recent
    - tags
```

Alternatively, you can use short notation in the front matter, if you don't need to change other properties of the
sidebar:

```yaml
sidebar:
  - recent
  - tags
```

Please note that the sidebar is only displayed if there is at least one widget added to the sidebar.

#### Sidebar position

Sidebar position for all pages can be specified in the `position` param under `[Params.sidebar]` section of the config
file. By default, `position` key equals `"right"` value, which means that the default sidebar position is on the right
side, if this not specified in the site config. Position can be changed to display the sidebar on the left if required:

```toml
[Params.sidebar]
  widgets = ["recent", "categories", "tags"]
  position = "left"
```

Sidebar position can be specified for home, list and single pages individually. Use the keys `positionHome`,
`positionList` and `positionSingle` with values `"left"`, `"right"` or `false` under `[Params.sidebar]` section of the
configuration file:

```toml
[Params.sidebar]
  positionHome = false
  positionList = "left"
  positionSingle = "right"
```

Sidebar position can be configured per page, by setting the `sidebar.position` parameter with one of the same values in
the page's front matter:

```yaml
sidebar:
  position: left
```

### Custom CSS

If you want to include custom CSS files, you need to assign an array of references in site config file (`config.toml` by
default) like following:

```toml
[Params]
  customCSS = ["css/custom.css"]
```

Of course, you can reference as many CSS files as you want. Their paths need to be relative to the `static` folder of
your Hugo site:

```toml
[Params]
  customCSS = ["css/custom.css", "css/another.css"]
```

All these CSS files will be added through the `head.html` partial after the built-in CSS file.

### Custom JS

You can add custom JavaScript files by assigning an array of references in site config file (`config.toml` by default)
like following:

```toml
[Params]
  customJS = ["js/custom.js"]
```

And of course, just like with custom CSS, you can reference as many JS files as you want. Their paths need to be
relative to the `static` folder of your Hugo site:

```toml
[Params]
  customJS = ["js/custom.js", "js/another.js"]
```

All custom JS files will be added before closing body tag of a `baseof.html` file.

### Featured Image

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

### Meta Fields

Meta fields are page meta information such as publish date, last modification date, reading time, categories, and even
more. Amnix comes with only one meta field to show post date/time, but you can always create your custom meta field.

You can enable meta fields globally or per page.

To activate meta fields globally you should use the `meta` config key with a list of meta field names as a value under
`[Params.Post]` section of the config file:

```toml
[Params.Post]
  meta = ["date"]
```

Or meta fields can be activated per page through front matter:

```yml
meta:
  - date
```

### Menus

**Amnix** supports main and side menus. The `main` menu is fully responsive and displayed in the site header. The `side`
secondary menu is displayed in a sidebar widget. To add a page to a menu, add a `menu: <menu>` parameter to the page's
front matter:

```yaml
menu: main # Add page to a main menu
```

You can also add a page to multiple menus by providing a list:

```yaml
menu: ["main", "side"] # Add page to main and side menus
```

**Note:** Don't forget to enable the `sidemenu` widget in the `widgets` configuration param if you want to use the
`side` menu.

**Note:** Please keep in mind that Amnix menus don't support nested items i.e. submenus.

*For more information, see [Menus](https://gohugo.io/content-management/menus/) in the Hugo documentation.*

### Footer Social Links

With **Amnix**, you have the option to display links to your social media profiles in the footer. To display them, set
up `[Params.Social]` parameters in your site config file.

Available social services: Email, Facebook, Twitter, Telegram, Instagram, Pinterest, VK, LinkedIn, GitHub, GitLab, Stack
Overflow, Mastodon, Medium

### Web App Manifest

[Web App Manifest](https://developers.google.com/web/fundamentals/web-app-manifest/) is a simple json file with basic
site info like name, description, icons, etc. This file tells the browser about your web application and how it should
behave when "installed" (as PWA) on the users mobile device or desktop.

To activate Web App Manifest, define `MANIFEST` as custom output format and include this for `home` Kind attribute in
your site config file. Here's how to make it.

First of all, you should define `MANIFEST` custom output format [`config.toml`]:

```toml
[outputFormats]
  [outputFormats.MANIFEST]
    mediaType = "application/json"
    baseName = "manifest"
    isPlainText = true
    notAlternative = true
```

Then, include `MANIFEST` output format for `home` Kind attribute [`config.toml`]:

```toml
[outputs]
  home = ["HTML", "RSS", "MANIFEST"]
```

After that, Web App Manifest file will be generated. Still, it's better to specify `[Params.Manifest]` params to make
sure that everything works as expected.

| Web App Manifest Property | `.Site.Params.Manifest` Key | Default Value | Type        |
| ------------------------- | --------------------------- | ------------- | ----------- |
| name                      | name                        | `.Site.Title` | required    |
| short_name                | shortName                   | `.Site.Title` | required    |
| display                   | display                     | `standalone`  | required    |
| start_url                 | startUrl                    | `/`           | required    |
| background_color          | backgroundColor             | `#33333a`     | recommended |
| theme_color               | themeColor                  | `#5b5b67`     | recommended |
| description               | description                 |               | recommended |
| orientation               | orientation                 |               | recommended |
| scope                     | scope                       |               | recommended |
| icons\*                   |                             |               | required    |

\* You can't customize manifest icons through config params, only by replacing icon files.

*To verify that your manifest file is configured properly and works well, run Hugo server and open Chrome DevTools
(Press F12 in Chrome) → Application → Manifest*

## Contributing

See [CONTRIBUTING.md](https://github.com/vimux/amnix/blob/master/CONTRIBUTING.md)

## License

**Amnix** is licensed under the [MIT License](https://github.com/vimux/amnix/blob/master/LICENSE).

* Social media icons based on [SuperTinyIcons](https://github.com/edent/SuperTinyIcons) (MIT License)
* CSS Reset based on [Bootstrap Reboot](https://github.com/twbs/bootstrap/blob/master/dist/css/bootstrap-reboot.css)
(MIT License)
