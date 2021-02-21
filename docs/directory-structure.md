# Directory Structure

Static Form is following Eleventy naming convention and directory structure with `src` as input folder. Let's see the `src` folder

```ASCII
.
└── src
    ├── _data
    ├── _includes
    │   └── theme
    ├── admin
    ├── forms
    ├── img
    └── styles

# Some folders and files are omitted

```

> The directory tree is made with [this awesome app](https://tree.nathanfriend.io)

- `src/_data`: Store global `.11tydata.js` or `.json` data file. [Read more...](https://www.11ty.dev/docs/data-global/)
- `src/_includes`: Place for Eleventy layouts / includes / component files. Files in this folder will not be processed as full [template files](https://www.11ty.dev/docs/languages/), but can be consumed by other templates. Changes to this folder will trigger Eleventy rebuild.
- `src/_includes/theme` (`theme` for short): Place where we put themes folder. See [theme](#).
- `src/admin`: Store template files for Netlify CMS entry point and config.
- `src/img`: Store media files, which copied to live site folder during build.
- `src/styles`: Store Tailwind configuration files.
- `src/forms`: Store posts (forms) Markdown file. Posts for each theme are placed subdirectory.

## Notable configuration files

- `.eleventy.js`: Eleventy configuration file.
- `package.json`: NPM configuration file.
- `postcss.config.js`: PostCSS configuration file.
- `.eleventyignore`: Eleventy ignored file list.
- `netlify.toml`: Netlify configuration file.
- `src/admin/config.yml.njk`: Netlify CMS `config.yml` mini-pipeline.
- `src/styles/tailwind.config.js`: Tailwind CSS configuration file.
- `src/styles/tailwind.css`: Tailwind CSS entry point.
