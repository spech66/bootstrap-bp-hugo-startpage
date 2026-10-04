# Bootstrap-BP hugo startpage

Lightweight Hugo startpage theme which provides out of the box best practices: about 3 KB of CSS, inline SVG icons and a WebP background, no CSS framework or icon font.
This theme is a combination of my [Bootstrap-BP hugo theme](https://github.com/spech66/bootstrap-bp-hugo-theme) and my [startpage](https://github.com/spech66/startpage).
Instead of rendering the items on-the-fly as in the startpage theme the **Bootstrap-BP hugo startpage** will generate a complete single page site.

Other themes by Sebastian Pech: [Bootstrap-BP](https://github.com/spech66/bootstrap-bp-hugo-theme), [Flex-BP hugo CV](https://github.com/spech66/flex-bp-hugo-cv),
[Bootstrap-BP hugo startpage](https://github.com/spech66/bootstrap-bp-hugo-startpage).

## Install the theme

With Git installed, run the following commands inside the Hugo site folder. If Hugo has not yet been installed, read the setup guide [here](https://gohugo.io/getting-started/quick-start/).

```sh
mkdir themes
cd themes
git clone https://github.com/spech66/bootstrap-bp-hugo-startpage.git
```

You can get a zip of the latest version of the theme from the [home page](https://github.com/spech66/bootstrap-bp-hugo-theme) and extract it to the themes folder.

## Theme settings

Most settings should be done with hugo specific variables. There are only a few (optional) additional `[params]`.

* `welcomeText = "Startpage!"` is the text above the search box
* `tagline = "All your links on one page"` (optional) is shown below the welcome text
* `startPageColumns = true` will show the start page in grouped lists, otherwise as icon tiles
* `background = "images/my-background.jpg"` (optional) is an image in your site's `assets/` folder. It is converted to WebP in two sizes. Default is the theme's background.

Custom styles go to `assets/css/custom.css` in your site. Colors and the glass effect are CSS variables (`--sp-glass`, `--sp-accent`, ...) in the theme's `assets/css/main.css`.

All activated search engines share one search field, the visitor switches between them below the field (the choice is remembered in the browser).

Activate the search engine you want to use (or add a new one).

```toml
[[params.searchEngines]]
  name = "Google"
  activated = true
  url = "https://www.google.com/search"

[[params.searchEngines]]
  name = "DuckDuckGo"
  activated = true
  url = "https://duckduckgo.com/"

[[params.searchEngines]]
  name = "Bing"
  activated = true
  url = "https://www.bing.com/search"

[[params.searchEngines]]
  name = "Baidu"
  activated = true
  url = "https://baidu.com/"
  searchkey = "kw"
```

![startPageColumns = false](https://raw.githubusercontent.com/spech66/bootstrap-bp-hugo-startpage/master/images/screenshot.png)

![startPageColumns = true](https://raw.githubusercontent.com/spech66/bootstrap-bp-hugo-startpage/master/images/screenshot2.png)

Define the links in a file in `data/links.yml`. This needs to be structured like this.

```yml
---
- group: Social media
  items:
    - title: reddit
      url: https://www.reddit.com
      icon: fab fa-reddit
    - title: Facebook
      url: https://www.facebook.com
      icon: fab fa-facebook
- group: Utilities
  items:
    - title: GitHub
      url: https://www.github.com
      icon: fab fa-github
```

Icons are [Font Awesome Free 5.15.4](https://fontawesome.com/v5/search?m=free) glyphs, rendered as inline SVG (no icon font, no Bootstrap or other CSS framework is loaded). Use the Font Awesome classes as before (`fab fa-github`, `fas fa-blog`, `far fa-heart`) or just the name (`github`). The glyphs are stored in `data/bpicons.json`, add your own icons there.

## Upgrading from older versions

Bootstrap 4 and the Font Awesome icon font are no longer part of the theme, `links.yml` and the settings keep working.

- The background moved from `static/images/bg.jpg` to `assets/images/bg.jpg`. A site that replaced it in `static/images/bg.jpg` should move the file to `assets/images/` and set `background = "images/bg.jpg"`, or use any other name.
- Own templates or content using Bootstrap classes need their own CSS in `assets/css/custom.css`.

## Sources

* Background image by [Mikael Gustafsson](https://www.artstation.com/artwork/Y2Wew)

Inspired by:

* [Reddit - r/startpages](https://www.reddit.com/r/startpages/)
* [Github - 0-Tikaro - Minimum Viable Startpage](https://github.com/0-Tikaro/minimum-viable-startpage), Searchbox code
* [Github - ViktorKare - startpage](https://github.com/ViktorKare/startpage)
