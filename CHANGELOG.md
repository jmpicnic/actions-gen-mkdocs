# Changelog

[![Keep a Changelog](https://img.shields.io/badge/Keep%20a%20Changelog-1.0.0-informational)](https://keepachangelog.com/en/1.0.0/)
[![Semantic Versioning](https://img.shields.io/badge/Sematic%20Versioning-2.0.0-informational)](https://semver.org/spec/v2.0.0.html)
![clq validated](https://img.shields.io/badge/clq-validated-success)

Keep the newest entry at top, format date according to ISO 8601: `YYYY-MM-DD`.

Categories, defined in [changemap.json](.github/clq/changemap.json):

- *major* release trigger:
  - `Changed` for changes in existing functionality.
  - `Removed` for now removed features.
- *minor* release trigger:
  - `Added` for new features.
  - `Deprecated` for soon-to-be removed features.
- *bugfix* release trigger:
  - `Fixed` for any bugfixes.
  - `Security` in case of vulnerabilities.

## [1.0.1] - 2023-12-07

### Fixed

- Use [awalsh128/cache-apt-pkgs-action](https://github.com/awalsh128/cache-apt-pkgs-action) to install packages with caching.
- Updated java version to use `corretto-21`
- Remove redundant installation of pandoc
- Minor changes for diagnostic logging, file permissions, etc...

## [1.0.0] - 2023-06-13

### Added

- action builds HTML site from Markdown/mkdocs sources
