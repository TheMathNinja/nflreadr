
<!-- README.md is generated from README.Rmd. Please edit that file -->

# nflreadr

<!-- badges: start -->
<!-- [![CRAN status](https://img.shields.io/cran/v/nflreadr?style=flat-square&logo=R&label=CRAN)](https://CRAN.R-project.org/package=nflreadr)  -->
<!-- [![Codecov test coverage](https://img.shields.io/codecov/c/github/nflverse/nflreadr?label=codecov&style=flat-square&logo=codecov)](https://codecov.io/gh/nflverse/nflreadr?branch=main) -->

[![Dev
status](https://img.shields.io/github/r-package/v/nflverse/nflreadr/main?label=dev%20version&style=flat-square&logo=github)](https://nflreadr.nflverse.com/)
[![Lifecycle:
experimental](https://img.shields.io/badge/lifecycle-experimental-orange.svg?style=flat-square)](https://lifecycle.r-lib.org/articles/stages.html)
[![R build
status](https://img.shields.io/github/workflow/status/nflverse/nflreadr/R-CMD-check?label=R%20check&style=flat-square&logo=github)](https://github.com/nflverse/nflreadr/actions)
[![nflverse
discord](https://img.shields.io/discord/591914197219016707.svg?color=5865F2&label=nflverse%20discord&logo=discord&logoColor=5865F2&style=flat-square)](https://discord.com/invite/5Er2FBnnQa)

<!-- badges: end -->

nflreadr is a low-level package for downloading data from nflverse
repositories.

## Installation

Install the development version from GitHub with:

``` r
install.packages("nflreadr", repos = "https://nflverse.r-universe.dev")

# or use remotes/devtools
# install.packages("remotes")
remotes::install_github("nflverse/nflreadr", ref = "dev")
```

## Usage

The main functions of `nflreadr` are prefixed with load.

``` r
library(nflreadr)
load_pbp(2020)
```

The following options help configure default `nflreadr` behaviours.

``` r
options(nflreadr.cache) # one of "memory", "filesystem", or "off"
options(nflreadr.prefer) # one of "qs" or "rds"
```

You can also configure `nflreadr` to display progress messages with the
`progressr` package, e.g.

``` r
progressr::with_progress(load_rosters(seasons = 2010:2020))
 |====================                               |  40%
```

## Roadmap

This package `must` include:

-   Functions for loading:
    -   general `rds_from_url()`, `qs_from_url()`, `parquet_from_url()`
        ✅
    -   pbp ✅
    -   player\_stats (aggregated by week) ✅
    -   schedules (aka Lee’s game data) ✅
    -   rosters ✅
    -   Next Gen Stats data ✅
    -   team\_stats (aggregated by week) \`waiting for
-   Document the available package options (currently nflreadr.cache and
    nflreadr.prefer) somewhere. ✅
-   Maybe in `nflreadr-package.R` created with `use_package_doc()`? Or
    just in the readme? ✅

------------------------------------------------------------------------

-   A hex sticker!
-   Data dictionaries and vignettes for all functions (still to-go:
    schedules, rosters, nextgen stats)
-   CRAN-standards/readiness (because we want to introduce it as a
    dependency for other packages)
