# Changelog

All notable changes to the Varbase Canvas Base recipe are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]
### Added
- Initialize the Varbase Canvas Base recipe. It installs the `canvas` and
  `canvas_override` modules, and nothing else.
- Take over the `canvas_override` install and the `drupal/canvas_override`
  requirement that `varbase_content_base` carried.

### Notes
- This recipe grants no permissions. The Drupal Canvas page and component library
  grants stay in `varbase_content_base`, where the content roles they belong to
  are defined, so the Vardot site templates that apply that recipe directly keep
  their Canvas permissions unchanged.

[Unreleased]: https://git.drupalcode.org/project/varbase_canvas_base/-/commits/1.0.x
