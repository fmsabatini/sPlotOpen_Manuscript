# sPlot open - An environmentally-balanced, open-access, global dataset of vegetation plots

<!-- usage note: edit the H1 title above to personalize the manuscript -->

[![HTML Manuscript](https://img.shields.io/badge/manuscript-HTML-blue.svg)](https://fmsabatini.github.io/sPlotOpen_Manuscript/)
[![PDF Manuscript](https://img.shields.io/badge/manuscript-PDF-blue.svg)](https://fmsabatini.github.io/sPlotOpen_Manuscript/manuscript.pdf)
[![GitHub Actions Status](https://github.com/fmsabatini/sPlotOpen_Manuscript/workflows/Manubot/badge.svg)](https://github.com/fmsabatini/sPlotOpen_Manuscript/actions)
[![Travis Build Status](https://travis-ci.com/fmsabatini/sPlotOpen_Manuscript.svg?branch=master)](https://travis-ci.com/fmsabatini/sPlotOpen_Manuscript)
<!-- usage note: delete CI badges above for services not used by your manuscript -->

## Manuscript description

<!-- usage note: edit this section. -->

This manuscript describes the construction of sPlot Open. sPlot Open is an environmentally-balanced subset of [sPlot - The Global Vegetation-Plot Database](https://www.idiv.de/en/splot.html) (version 2.1), which will be released as open-access. 

Links to the rendered version of this manuscript:  
+ **HTML manuscript** at https://fmsabatini.github.io/sPlotOpen_Manuscript/
+ **PDF manuscript** at https://fmsabatini.github.io/sPlotOpen_Manuscript/manuscript.pdf

**This manuscript is under construction**  

See the sister project [sPlotOpen_code](https://github.com/fmsabatini/sPlotOpen_Code/) to see how the sPlot Open database is being constructed  

### Wiki - How tos:
Check the project's [Wiki](https://github.com/fmsabatini/sPlotOpen_Manuscript/wiki) for help on:  
[1. Accessing the manuscript](https://github.com/fmsabatini/sPlotOpen_Manuscript/wiki/1.-Accessing-the-manuscript)  
[2. How to contribute edits using GitHub’s browser interface](https://github.com/fmsabatini/sPlotOpen_Manuscript/wiki/2.-Edit-the-manuscript-using-GitHub%E2%80%99s-browser-interface)  
[3. Alternative to using GitHub (not recommended)](https://github.com/fmsabatini/sPlotOpen_Manuscript/wiki/3.-Alternative-to-using-GitHub-(not-recommended))  
[4. Editing personal and affiliation information](https://github.com/fmsabatini/sPlotOpen_Manuscript/wiki/4.-Editing-personal-and-affiliation-information)  
[5. How to open issues, suggest ideas and discuss problems](https://github.com/fmsabatini/sPlotOpen_Manuscript/wiki/5.-How-to-open-issues,-suggest-ideas-and-discuss-problems)  
[6. Approve Submission](https://github.com/fmsabatini/sPlotOpen_Manuscript/wiki/6.-Approve-Submission)

Or see this Short Video - [**Editing with Manubot**](https://manubot.org/docs/getting-started.html). Just, *don't forget to click 'commit changes' after your edits!!*

### sPlot - The Global Vegetation-Plot Database
_Below, a list of relevant papers describing, or using sPlot:_  
- [Bruelheide et al. 2019 - sPlot – A new tool for global vegetation analyses - J Vegetation Science](https://onlinelibrary.wiley.com/doi/10.1111/jvs.12710)  
- [Bruelheide et al. 2018 - Global trait–environment relationships of plant communities - NatEcoEvo](https://www.nature.com/articles/s41559-018-0699-8)  
- [Weigand et al. 2019 - Global fern and lycophyte richness explained: How regional and local factors shape plot richness - J Biogeography](https://onlinelibrary.wiley.com/action/showCitFormats?doi=10.1111%2Fjbi.13782)  
- [van der Sande et al. 2020 - Similar factors underlie tree abundance in forests in native and alien ranges - Global Ecology & Biogeography](https://onlinelibrary.wiley.com/doi/full/10.1111/geb.13027?af=R)  


_sPlot is an initiative of [iDiv - The German Centre for Integrative Biodiversity Research](https://www.idiv.de/en/index.html)_

## Manubot

<!-- usage note: do not edit this section -->

This manuscript is created and edited using Manubot. Manubot is a system for writing scholarly manuscripts via GitHub.
Manubot automates citations and references, versions manuscripts using git, and enables collaborative writing via GitHub.
An [overview manuscript](https://greenelab.github.io/meta-review/ "Open collaborative writing with Manubot") presents the benefits of collaborative writing with Manubot and its unique features.
The [rootstock repository](https://git.io/fhQH1) is a general purpose template for creating new Manubot instances, as detailed in [`SETUP.md`](SETUP.md).
See [`USAGE.md`](USAGE.md) for documentation how to write a manuscript.

Please open [an issue](https://git.io/fhQHM) for questions related to Manubot usage, bug reports, or general inquiries.

### Repository directories & files

The directories are as follows:

+ [`content`](content) contains the manuscript source, which includes markdown files as well as inputs for citations and references.
  See [`USAGE.md`](USAGE.md) for more information.
+ [`output`](output) contains the outputs (generated files) from Manubot including the resulting manuscripts.
  You should not edit these files manually, because they will get overwritten.
+ [`webpage`](webpage) is a directory meant to be rendered as a static webpage for viewing the HTML manuscript.
+ [`build`](build) contains commands and tools for building the manuscript.
+ [`ci`](ci) contains files necessary for deployment via continuous integration.

### Local execution

The easiest way to run Manubot is to use [continuous integration](#continuous-integration) to rebuild the manuscript when the content changes.
If you want to build a Manubot manuscript locally, install the [conda](https://conda.io) environment as described in [`build`](build).
Then, you can build the manuscript on POSIX systems by running the following commands from this root directory.

```sh
# Activate the manubot conda environment (assumes conda version >= 4.4)
conda activate manubot

# Build the manuscript, saving outputs to the output directory
bash build/build.sh

# At this point, the HTML & PDF outputs will have been created. The remaining
# commands are for serving the webpage to view the HTML manuscript locally.
# This is required to view local images in the HTML output.

# Configure the webpage directory
manubot webpage

# You can now open the manuscript webpage/index.html in a web browser.
# Alternatively, open a local webserver at http://localhost:8000/ with the
# following commands.
cd webpage
python -m http.server
```

Sometimes it's helpful to monitor the content directory and automatically rebuild the manuscript when a change is detected.
The following command, while running, will trigger both the `build.sh` script and `manubot webpage` command upon content changes:

```sh
bash build/autobuild.sh
```

### Continuous Integration

Whenever a pull request is opened, CI (continuous integration) will test whether the changes break the build process to generate a formatted manuscript.
The build process aims to detect common errors, such as invalid citations.
If your pull request build fails, see the CI logs for the cause of failure and revise your pull request accordingly.

When a commit to the `master` branch occurs (for example, when a pull request is merged), CI builds the manuscript and writes the results to the [`gh-pages`](https://github.com/fmsabatini/sPlotOpen_Manuscript/tree/gh-pages) and [`output`](https://github.com/fmsabatini/sPlotOpen_Manuscript/tree/output) branches.
The `gh-pages` branch uses [GitHub Pages](https://pages.github.com/) to host the following URLs:

+ **HTML manuscript** at https://fmsabatini.github.io/sPlotOpen_Manuscript/
+ **PDF manuscript** at https://fmsabatini.github.io/sPlotOpen_Manuscript/manuscript.pdf

For continuous integration configuration details, see [`.github/workflows/manubot.yaml`](.github/workflows/manubot.yaml) if using GitHub Actions or [`.travis.yml`](.travis.yml) if using Travis CI.

## License

<!--
usage note: edit this section to change the license of your manuscript or source code changes to this repository.
We encourage users to openly license their manuscripts, which is the default as specified below.
-->

[![License: CC BY 4.0](https://img.shields.io/badge/License%20All-CC%20BY%204.0-lightgrey.svg)](http://creativecommons.org/licenses/by/4.0/)
[![License: CC0 1.0](https://img.shields.io/badge/License%20Parts-CC0%201.0-lightgrey.svg)](https://creativecommons.org/publicdomain/zero/1.0/)

Except when noted otherwise, the entirety of this repository is licensed under a CC BY 4.0 License ([`LICENSE.md`](LICENSE.md)), which allows reuse with attribution.
Please attribute by linking to https://github.com/fmsabatini/sPlotOpen_Manuscript.

Since CC BY is not ideal for code and data, certain repository components are also released under the CC0 1.0 public domain dedication ([`LICENSE-CC0.md`](LICENSE-CC0.md)).
All files matched by the following glob patterns are dual licensed under CC BY 4.0 and CC0 1.0:

+ `*.sh`
+ `*.py`
+ `*.yml` / `*.yaml`
+ `*.json`
+ `*.bib`
+ `*.tsv`
+ `.gitignore`

All other files are only available under CC BY 4.0, including:

+ `*.md`
+ `*.html`
+ `*.pdf`
+ `*.docx`

Please open [an issue](https://github.com/fmsabatini/sPlotOpen_Manuscript/issues) for any question related to licensing.
