# texlive-min-action
A GitHub action that installs the latest texlive version and runs chktex and latexmk

## Usage
**Basic GitHub action file:**
```yaml
on: [push]

jobs:
  hello_world_job:
    runs-on: ubuntu-latest
    name: example usage of texlive-min-action
    steps:
      - uses: actions/checkout@v3
      - uses: lucasmchoi/texlive-min-action@v2022.05.01
        with:
          texfile: 'main'
          tlmgrpackages: 'hyperref babel'
```
This example GitHub action file would install the latest texlive version with `scheme-basic` and the packages `hyperref` and `babel`. After that it would run `chktex` and `latexmk` on `main.tex`.

### Inputs
- `texlivescheme`
  - **description:** texlive selected_scheme for installation
  - **required:** false
  - **default:** 'scheme-basic'
- `texfile`
  - **description:** name of main tex file
  - **required:** false
  - **default:** 'main'
- `aptpackages`
  - **description:** additional apt packages to install
  - **required:** false
- `tlmgrpackages`
  - **description:** additional tlmgr packages to install
  - **required:** false
- `chktexargs`
  - **description:** arguments for chktex
  - **required:** false
  - **default:** '-v2'
- `latexmkargs`
  - **description:** arguments for latexmk
  - **required:** false
  - **default:** '-pdf'
- `artifactretention`
  - **description:** retention duration of pdf
  - **required:** false
  - **default:** '90'

## License
Copyright © 2022 [Luca Choi](https://www.github.com/lucasmchoi)

This work is licensed under [AGPL v3](/LICENSE)
