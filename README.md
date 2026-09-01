[![Varbase](https://raw.githubusercontent.com/Vardot/varbase/11.0.x/images/varbase-logo.png)](https://www.drupal.org/project/varbase)

# Varbase Canvas Base
[![pipeline status](https://git.drupalcode.org/project/varbase_canvas_base/badges/1.0.x/pipeline.svg)](https://git.drupalcode.org/project/varbase_canvas_base/-/pipelines)
[![Varbase Canvas Base](https://img.shields.io/badge/Varbase%20Canvas%20Base-1.0.x--dev-0d6efc?labelColor=001d38&style=flat-square)](https://git.drupalcode.org/project/varbase_canvas_base/-/pipelines?ref=1.0.x)
[![Automated Functional Testing](https://git.drupalcode.org/project/varbase_project/badges/11.0.x/pipeline.svg)](https://git.drupalcode.org/project/varbase_project/-/pipelines)

A foundational recipe for Drupal Canvas in Varbase. It is the one place that owns
the Drupal Canvas page-building setup — the Canvas Override module and the Canvas
permissions granted to the Varbase roles — instead of that setup being spread
across the other `varbase_*_base` recipes.

## Features

### Modules
- **[canvas](https://www.drupal.org/project/canvas)** — Drupal Canvas: the
  `canvas_page` entity, the component library, patterns, content templates and
  the page-region (header / footer) editor.
- **[canvas_override](https://www.drupal.org/project/canvas_override)** —
  per-content Canvas layout editing on the full view mode of selected content
  types, with a fallback to the shared content template.

### Permissions

| Role | Canvas pages | Component library and templates |
|---|---|---|
| Content editor | create, edit | — |
| Content admin | create, edit, publish auto-saves | folders, patterns |
| Site admin | create, edit, delete, publish auto-saves | components, content templates, folders, page template, patterns, global regions |

Two Canvas permissions are deliberately left ungranted. `administer code
components` allows JavaScript to be executed and is marked `restrict access` by
Drupal Canvas. `administer brand kit` is a per-site branding decision. Grant
either to a named role per site when it is genuinely needed.

The `canvas_override` module's own permissions (`use canvas override`,
`reset canvas layout`, `edit canvas default template`,
`administer canvas override`) are not granted here either. No Varbase recipe has
ever granted them; whether they should be is tracked as its own issue rather than
decided as a side effect of this recipe.

## Scope

This recipe installs no content types and no fields.

It is applied by **`varbase_starter`** only. The Vardot site templates
(`educare`, `horizonaid`, `rightup`) deliberately do not require it — they apply
`varbase_content_base` and `varbase_media_base` directly, and the `canvas` module
install stays in `varbase_media_base` so those templates keep working unchanged.

Two neighbouring pieces are deliberately left where they are:

- `canvas_translate` stays in `varbase_i18n_base` — it is a language concern.
- The `canvas_html_inline` / `canvas_html_block` text format permissions stay in
  `varbase_editor_base` — they are an editor concern.
- `canvas_icon_picker` belongs to `varbase_admin_base`.

## Installation

Add the recipe using composer:
```
composer require drupal/varbase_canvas_base:~1.0.0
```

Change directory to `/web` or `/docroot`

Run the Drupal recipe bash script:
```
bash core/scripts/drupal recipe recipes/varbase_canvas_base
```

or

Run the Drush recipe command:
```
drush recipe ../recipes/varbase_canvas_base
```

## Maintainers

- [Vardot](https://www.drupal.org/vardot)

## License

GPL-2.0-or-later
