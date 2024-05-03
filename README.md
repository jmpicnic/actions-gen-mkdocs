# action-build-mkdocs

This action builds [mkdocs Markdown](https://www.mkdocs.org/) documents into an HTML site. By default it also creates the `techdocs-metadata.json` that backstage requires for publication.

## Usage

This action is intended to be used as part of a workflow that builds and publishes backstage documents to [Flexport's Backstage Portal](https://backstage.gess.flexport.internal) but it is not tied to it. It can be used stand alone to just generate HTML sites from mkdocs structured documentation.

### Inputs

* `docs-dir`: The directory where the `mkdocs.yml` and the `requirements.txt` files are to be found and where the Markdown content needs to be located.
  * Default: `.`, the root directory of the repository
* `site-target-dir`: The directory where the HTML site is to be generated, **RELATIVE** to the value specified in `docs-dir`
  * Default: `./gen-site`
* `requirements-file-name`: The name of the python pip requirements file containing all the extensions and plugins for mkdocs **RELATIVE** to `docs-dir`.
  * Default: `requirements.txt`

  Note that this action supports some extensions that require non-python tools, installed separately. The ones currently supported are:

  * [PlantUml](https://plantuml.com/) for diagraming
  * [Latex/Texlive](https://www.tug.org/texlive/) For math formatting
  * [Graphviz](https://graphviz.org/) as support for PlantUml and to access other types of diagrams.
  * [Pandoc](https://pandoc.org/) for format conversions. It includes `pandoc-citeproc` to support BibTex style citations.

    If your mkdocs configuration needs other non-python tools, it is your responsibility to configure them at the right place in your workflow before calling this action.

* `mkdocs-file-name`: The name of the mkdocs config file relative to `docs-dir`
  * Default: `mkdocs.yml`
<!-- * `for-techdocs`: If `Yes`, `yes`, `True` or `true` it will generate the required `techdocs_metadata.json` file for Backstage. 
  * Default: `True` -->

### Outputs

* `generated-site`: The path to the directory of the generated site, **RELATIVE** to the root of the repository.

### Versions

This action follows Semantic versioning.

As an example:

* v1 : Latest of the 1.x.y series
* v1.0: Latest of the 1.0.y series
* v1.0.0: Current version

### Example Workflow

```yaml
---
name: commerce-search-docs-gen-publish
on:
  push:
    branches:
      - main
jobs:
  generate-domain-docs:
    name: generate-docs
    runs-on: default
    steps:
      - name: Checkout code
        uses: actions/checkout@v3
      - name: Generate Docs
        id: gen-docs
        uses: jmpicnic/actions-gen-mkdocs@v1
        with:
          docs-dir: "./docs"
          site-target-dir: "site"
          requirements-file-name: special-requirements.txt
          mkdocs-file-name: mkdocs-ghpages.yml
          for-techdocs: False
      - name: Upload Pages artifact
        uses: actions/upload-pages-artifact@v2 
        with:
          path: ${{ steps.generate-docs.outputs.generated-site }}
```
