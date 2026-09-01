# Changelog

All notable changes to the Varbase Canvas Base recipe are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]
### Added
- Initialize the Varbase Canvas Base recipe. It installs `canvas` and
  `canvas_override`, and grants the Drupal Canvas page, component library,
  pattern, template and global region permissions to the `content_editor`,
  `content_admin` and `site_admin` roles.
- Take over the `canvas_override` install, the `drupal/canvas_override`
  requirement and the Canvas permission grants that `varbase_content_base`
  carried, so the Canvas setup lives in one recipe.

[Unreleased]: https://git.drupalcode.org/project/varbase_canvas_base/-/commits/1.0.x
