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

## [1.1.13] - 2025-07-08

### Fixed

- Removed version outputs

## [1.1.12] - 2025-07-08

### Fixed

- Removed graphviz as not needed if plantuml is run with

## [1.1.11] - 2025-07-08

### Fixed

- Moved back to latest of apt install action.

## [1.1.10] - 2025-07-08

### Fixed

- Added more dot installation debug output.

## [1.1.9] - 2025-07-08

### Fixed

- More comprehensive error reporting for `dot` installation.

## [1.1.8] - 2025-07-08

### Fixed

- Print `which dot` command output.

## [1.1.7] - 2025-07-08

### Fixed

- Added `set -x` and IDs to all steps for better debugging and logging.

## [1.1.6] - 2025-07-08

### Fixed

- Upgraded plantuml to version 1.2025.4
- Pinned `awalsh128/cache-apt-pkgs-action` to version 1.5.0 to avoid issues with `apt-fast` installation.

## [1.1.5] - 2025-03-07

### Fixed

- Fixed Changelog

## [1.1.4] - 2025-03-07

### Fixed

- Echo Python version

## [1.1.3] - 2025-03-07

### Fixed

- Fixed parameter inputs.python-version reference

## [1.1.2] - 2025-03-07

### Fixed

- Bump Python version to 3.12

## [1.1.1] - 2024-05-03

### Fixed

- Markdown linting error in `README.md`

## [1.1.0] - 2024-05-03

### Added

- Installed package `pandoc-citeproc` to support BibTex style citations.

## [1.0.3] - 2023-12-07

### Fixed

- Fixed Plantuml download option

## [1.0.2] - 2023-12-07

### Fixed

- Missing `shell` in `action.yml` step

## [1.0.1] - 2023-12-07

### Fixed

- Use [awalsh128/cache-apt-pkgs-action](https://github.com/awalsh128/cache-apt-pkgs-action) to install packages with caching.
- Updated java version to use `corretto-21`
- Remove redundant installation of pandoc
- Minor changes for diagnostic logging, file permissions, etc...

## [1.0.0] - 2023-06-13

### Added

- action builds HTML site from Markdown/mkdocs sources
