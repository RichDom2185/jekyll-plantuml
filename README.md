# Jekyll PlantUML Plugin

> View the demo [here](https://richdom2185.github.io/jekyll-plantuml).

GitHub Pages only allows a specific set of [plugins](https://pages.github.com/versions/) to run, hence, additional plugins that are in the form of RubyGems are not supported.

This plugin transforms PlantUML code blocks into PlantUML diagrams. It is a Jekyll plugin that uses the [PlantUML](http://plantuml.com/) tool to generate the diagrams.

Benefits:

* Fully compatible with GitHub Pages
* Easily customisable to your needs
* Composable API with all my [other Jekyll plugins](https://github.com/RichDom2185/jekyll-showcase)

## Add it to your site

### Step 1: Copy the required files

Copy the following files to your site's `_includes` folder:

* `plantuml.liquid`: The main parser to generate the PlantUML diagrams
* `capturehtml.liquid`: Un-escapes HTML special characters, used to parse HTML tags inside pre-formatted code blocks

If you already have a copy of `capturehtml.liquid` from my other plugins, you can reuse that file, and only copy `plantuml.liquid`.

### Step 2: Include it in your site

#### As a HTML layout

Simply include it in any of the layouts you want to add support for:

**Recommended:** Reassign the layout's `content` variable. This approach ensures composability should you want to include additional plugins/perform additional processing on the content.

```html
{% capture content %}{% include plantuml.liquid html=content %}{% endcapture %}
<!-- Some other stuff... -->
{{ content }}
```

**Alternative:** Replace `{{ content }}` directly:

* Before:

  ```html
  <!-- Some other stuff... -->
  {{ content }}
  ```

* After:

  ```html
  <!-- Some other stuff... -->
  {% include plantuml.liquid html=content %}
  ```

## Usage

Simply write your PlantUML code blocks as you would normally:

````markdown
```plantuml
Alice -> Bob: Hi there!
Bob --> Alice: Hello to you too!
```
````

**Note:** Both `plantuml` and `puml` are supported as language tags.

The plugin will automatically convert the PlantUML code blocks to a placeholder image, and when the page is loaded, a tiny bit of JavaScript will replace the placeholder with the actual PlantUML diagram.

![Resulting Diagram](https://www.plantuml.com/plantuml/png/Syp9J4vLqBLJSCfFibBmo5GeoKWjIbNa0d8LT872ZY1ve4HgJaw-Gac-GcL-AP3ALmG0)

This does mean that JavaScript must be enabled for the diagrams to be displayed correctly.
