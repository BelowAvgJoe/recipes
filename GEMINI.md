# Recipes Project Overview

This repository is a collection of recipes maintained as an [Antora](https://antora.org/) documentation component. It contains various recipes categorized by type (meats, sauces, sides, etc.) and is structured to be published as a static documentation site.

## Project Structure

- `docs/`: The main Antora documentation source.
  - `antora.yml`: The component configuration file (name: `cook_this`).
  - `modules/`: Contains the recipe modules.
    - `meat/`, `sauces/`, `sides/`, `soups/`, `staples/`, `tryThese/`: Categorized recipe pages.
    - `welcome/`: Contains the landing page (`index.adoc`) and the navigation file (`nav.adoc`).
- `allFiles/`: A collection of recipes in both `.adoc` and `.pdf` formats. This directory seems to contain a flat list of recipes, possibly for easier manual access or legacy purposes.
- `recipes/`: An additional directory, likely for raw recipe data or future expansion.

## Key Files

- `docs/antora.yml`: Defines the Antora component and its metadata.
- `docs/modules/welcome/nav.adoc`: Manages the navigation structure for the documentation site.
- `docs/modules/*/pages/*.adoc`: The individual recipe files written in AsciiDoc.

## Development and Usage

### Adding a New Recipe
1.  Create a new `.adoc` file in the appropriate module's `pages/` directory (e.g., `docs/modules/meat/pages/my-recipe.adoc`).
2.  Follow the existing template (metadata at the top, `== Ingredients`, `== Directions`).
3.  Add a reference to the new recipe in `docs/modules/welcome/nav.adoc` to make it appear in the site navigation.

### Building the Site
This project is designed to be built using Antora. While there is no local `package.json` with scripts, you would typically run Antora against this repository (or a playbook file referencing it) to generate the static site.

```bash
# Example Antora command (requires Antora CLI)
antora generate site.yml
```

### Conventions
- **Format:** All recipes should be written in AsciiDoc (`.adoc`).
- **Metadata:** Include standard Antora attributes (keywords, navtitle, etc.) at the top of each page.
- **Images:** Store images in the `images/` directory within the respective module and reference them using the `image::` macro.
