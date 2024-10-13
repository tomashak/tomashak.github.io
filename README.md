# Jekyll Project

This is a Jekyll project that utilizes GitHub Pages to host a static website. The project structure is as follows:

```
jekyll-project
├── _config.yml
├── _posts
│   └── 2023-10-01-sample-post.md
├── _layouts
│   └── default.html
├── _includes
│   └── header.html
├── assets
│   ├── css
│   │   └── style.css
│   └── js
│       └── script.js
├── .github
│   └── workflows
│       └── github-pages.yml
├── index.md
└── README.md
```

## Files

### `_config.yml`

This file is the configuration file for the Jekyll site. It contains settings and options for the site, such as the site title, theme, and plugins.

### `_posts/2023-10-01-sample-post.md`

This file is a sample Markdown file that represents a blog post. It follows the naming convention `YYYY-MM-DD-title.md` and contains the content of the blog post.

### `_layouts/default.html`

This file is a layout template for the Jekyll site. It defines the structure and styling of the site's pages. Other pages can inherit from this layout and customize it as needed.

### `_includes/header.html`

This file is an include file that contains the HTML code for the site's header. It can be included in multiple pages to maintain consistency.

### `assets/css/style.css`

This file is a CSS file that contains the styles for the Jekyll site. It defines the visual appearance of the site, such as colors, fonts, and layout.

### `assets/js/script.js`

This file is a JavaScript file that contains the scripts for the Jekyll site. It adds interactivity and dynamic behavior to the site.

### `.github/workflows/github-pages.yml`

This file is a GitHub Actions workflow file. It defines a workflow that automatically deploys the Jekyll site to GitHub Pages whenever changes are pushed to the repository.

### `index.md`

This file is the main Markdown file for the Jekyll site. It represents the homepage of the site and can contain content such as an introduction or summary.

### `README.md`

This file contains the documentation for the project. It provides information about the project, its purpose, and how to set it up or contribute to it.

Please note that this file is intentionally left blank.