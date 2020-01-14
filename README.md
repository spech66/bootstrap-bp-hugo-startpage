# Bootstrap-BP hugo startpage

Bootstrap based Hugo startpage theme which provides out of the box best practices.
This theme is a combination of my [Bootstrap-BP hugo theme](https://github.com/spech66/bootstrap-bp-hugo-theme) and my [startpage](https://github.com/spech66/startpage).
Instead of rendering the items on-the-fly as in the startpage theme the **Bootstrap-BP hugo startpage** will generate a complete single page site.

Other themes by Sebastian Pech: [Bootstrap-BP](https://github.com/spech66/bootstrap-bp-hugo-theme), [Materialize-BP](https://github.com/spech66/materialize-bp-hugo-theme),
[Bootstrap-BP hugo startpage](https://github.com/spech66/bootstrap-bp-hugo-startpage).

## Install the theme

With Git installed, run the following commands inside the Hugo site folder. If Hugo has not yet been installed, read the setup guide [here](https://gohugo.io/overview/installing/).

```sh
mkdir themes
cd themes
git clone https://github.com/spech66/bootstrap-bp-hugo-startpage.git
```

You can get a zip of the latest version of the theme from the [home page](https://github.com/spech66/bootstrap-bp-hugo-theme) and extract it to the themes folder.

## Theme settings

Most settings should be done with hugo specific variables. There are only a few (optional) additional `[params]`.

* `welcomeText = "Startpage!"` is the text above the search box
* `startPageColumns = true` will show the start page in grouped lists

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

Icons are taken from [Font Awesome](https://fontawesome.com/icons?d=gallery).

## Sources

* Background image by [Mikael Gustafsson](https://www.artstation.com/artwork/Y2Wew)

Inspired by:

* [Reddit - r/startpages](https://www.reddit.com/r/startpages/)
* [Github - 0-Tikaro - Minimum Viable Startpage](https://github.com/0-Tikaro/minimum-viable-startpage), Searchbox code
* [Github - ViktorKare - startpage](https://github.com/ViktorKare/startpage)
