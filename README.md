# Goal  

Add a section to home page with most recent visuals (the "featured.png" for posts, projects, AND talks) in a clean grid. Clicking on the image takes you to its home page.  

- Use [hugrid](https://github.com/aerohub/hugrid) for general layout and functionality  
- Use existing syntax to fetch images and links. See 
  - wowchemy/layouts/partials/li_card.html
  - wowchemy/layouts/partials/portfolio_li_showcase.html
  - wowchemy/layouts/partials/widgets/portfolio.html
  
## Wowchemy Widget Starter Template

**Looking to build and publish a [Wowchemy](https://wowchemy.com) widget that doesnโt exist yet?**

_[**Wowchemy**](https://wowchemy.com) makes it easy to create a beautiful website for free. Edit your site in Markdown, Jupyter, or RStudio, generate it with Hugo, and deploy with GitHub or Netlify. Customize anything on your site with widgets, themes, and language packs._

### ๐ Core Concepts

- Each Wowchemy widget consists of an HTML file
- You may use [Go Templating](https://gohugo.io/templates/introduction/) and [Bootstrap](https://getbootstrap.com/docs/4.5/layout/grid/) layouts to design the widget HTML

### ๐งโ๐จ Create a Widget

1. Click the [_Use This Template_](https://github.com/wowchemy/wowchemy-widget-starter/generate) button on GitHub
   1. Name your repository `wowchemy-widget-<WIDGET-NAME>` where `<WIDGET-NAME>` is an appropriate name for your widget
1. Browse your new GitHub project, click the  `go.mod` file, and then the โ๏ธ pencil button to edit it
   1. Replace the placeholder URL in `go.mod` with your new GitHub URL in the form `module github.com/<USERNAME>/wowchemy-widget-<WIDGET-NAME>` where `<USERNAME>` is your GitHub username and `<WIDGET-NAME>` is the name of the widget
   1. Scroll to the bottom and click _Commit Changes_ to save
1. Browse to the `layouts/partials/widgets/` folder, click `my-widget.html`, and click the โ๏ธ pencil button to edit it
   1. Rename `my-widget.html` in the text box to a unique ID in the form `github.<USERNAME>.<WIDGET-NAME>.html`, again replacing  `<USERNAME>` with your GitHub username and `<WIDGET-NAME>` with your widget name
   1. Scroll to the bottom and click _Commit Changes_ to save
1. Edit the HTML for your new widget
   - You may use [Go Templating](https://gohugo.io/templates/introduction/) and [Bootstrap](https://getbootstrap.com/docs/4.5/layout/grid/) layouts
   - You can access page and section (widget instance) variables using `$page` and `$section`, respectively
   - Check out the [built-in widgets](https://github.com/wowchemy/wowchemy-hugo-modules/tree/master/wowchemy/layouts/partials/widgets) for inspiration

#### Example

Say your GitHub username is `pikachu` and you wish to create a widget named `pokemon`:

1. We click _Use This Template_ and enter `wowchemy-widget-pokemon` as the project name
1. We replace the first line of `go.mod` with `module github.com/pikachu/wowchemy-widget-pokemon`
1. We browse to the `layouts/partials/widgets/` folder, and rename `my-widget.html` to `github.pikachu.pokemon.html`
1. We customize the HTML in `github.pikachu.pokemon.html`
1. We add the widget to our site and share the widget with the community following the guide below

### ๐ Add the Widget to your Site

1. Install your widget in your site by referencing it at the bottom of your `config/_defaults/config.toml`:
   ```toml
   # At the bottom of your `config.toml` is a Module section:
   [module]

     # Your existing modules will appear here.

     # Add your widget's GitHub URL below.
     # Replace <USERNAME> and <WIDGET-NAME> with your GitHub username and widget name, respectively.
     [[module.imports]]
       path = "github.com/<USERNAME>/wowchemy-widget-<WIDGET-NAME>"
   ```
1. Create an instance of your widget in `home/`, for example let's create `home/my-widget.md`:
   ```markdown
   ---
   # Replace <USERNAME> and <WIDGET-NAME> with your GitHub username and widget name, respectively.
   widget: 'github.<USERNAME>.<WIDGET-NAME>'

   # This file represents a page section.
   headless: true

   # Order that this section appears on the page.
   weight: 1

   title: Hello
   ---

   Welcome to my new widget!
   ```

### ๐ข Share your widget

Share your widget with the community on [Discord](https://discord.gg/z8wNYzb) and [Twitter](https://twitter.com/intent/tweet?text=I%27m%20creating%20a%20beautiful%20website%20widget%20using%20the%20free%20%E2%9D%A4%EF%B8%8F%2C%20open%20source%20%40wowchemy%20Website%20Builder%20for%20%40GoHugoIO%20by%20%40GeorgeCushen%20%E2%9C%A8%20Have%20some%20feedback%3F%20Please%20comment%20%F0%9F%A4%97&hashtags=MadeWithWowchemy&url=https://wowchemy.com/).
