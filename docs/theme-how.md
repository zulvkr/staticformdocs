# What is theme exactly?

Theme is an Eleventy layout + Netlify CMS preview template. Every forms are using theme as their layout and every theme should have a preview template to allow intuitive form building experience. 

We can opt-out not making the preview template, but its kind of defeating the purpose of Static Form. So, making a complete theme need some consideration how to share the template code between 2 different sides to avoid a lot of rewriting.

We use javascript template (+ nunjucks layout), and `preact/htm` to make basic theme. But other templating engine that can be used in both Eleventy and React (Netlify CMS) is also viable choice.

Other known example is using [Nunjucks in both sides](https://github.com/hankchizljaw/hylia/blob/master/src/admin/previews.js) and using [`preact/htm` in both sides](https://markus.oberlehner.net/blog/setting-up-eleventy-with-preact-and-htm/).

When making theme, there are some conventions to follow:

## Directory structure

```markdown
theme
└── my-theme-name
    ├── index[.11ty.js/.njk/...]
    ├── components (optional)
    ├── preview
    │   ├── index.js
    │   └── components (optional)
    ├── config.yml
    └── *.tailwind.css (optional)
```
- `my-theme-name`: theme folder name is an important point. This name is referred in many configuration file to allow easy theme installation. Don't use white space to avoid unexpected behavior.
- `index[.11ty.js/.njk/...]`: Eleventy layout that will be used by posts (forms).
- `components`: Store component files refered by index.
- `preview/index.js`: Netlify CMS preview template. This file should be copied to `_site/admin/my-theme-name` during build along with necessary components. Static Form will register them as preview template automatically.
- `config.yml`: Netlify CMS configuration file. This file will be concatenated with main config.yml file during build.
- `*.tailwind.css`: Extra components / utilities for Tailwind CSS. Any files with `.tailwind.css` extension in a theme folder will be imported by PostCSS.

## theme.eleventy.js

```JS
module.exports = function(eleventyConfig) {
  eleventyConfig.addLayoutAlias("basic", "theme/basic/index.njk");

  eleventyConfig.addPassthroughCopy({
    "src/_includes/theme/my-theme-name/preview/": "./admin/preview/my-theme-name/"
  });
};
```

Static Form will look for `theme.eleventy.js` file in a theme folder and add it as an Eleventy plugin.

The important point here is using `addPassthroughCopy()` to copy `index.js` Template Preview file along with its components to `./admin/preview/my-theme-name`. Static Form will look for `index.js` in that specific location.

## config.yml

```YAML
collections: # This line will be deleted during build
  - label: Basic Forms
    name: basic
    folder: src/forms/basic
    preview_path: "forms/basic/{{'{{slug}}'|safe}}"
    create: true
    fields:
      - label: Layout
        name: layout
        widget: hidden
        default: basic  # --> your layout alias
      - label: Title
        name: title
        widget: string
      - label: Date
        name: date
        widget: datetime
```

Static Form will `config.yml` file in a theme folder and concatenate it with the main `config.yml` file stored in `src/admin`.

Hit [Netlify CMS documentation](https://www.netlifycms.org/docs/widgets/) to see all available configuration.