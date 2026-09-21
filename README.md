# cfcdae

**C**ompanion to *A **F**irst **C**ourse in **D**esign and **A**nalysis of
**E**xperiments*, by Gary W. Oehlert.

The book, its second-edition draft, and extended R examples are freely
available from the author's page:

> **<https://users.stat.umn.edu/~gary/Book.html>**

This R package, written by Professor Oehlert, contains the 155 data sets from
the second edition along with functions used throughout the book: linear
contrasts, pairwise and Dunnett comparisons, model effects, interaction and
side-by-side plots, power and sample size, tools for two-series factorials, and
Hasse diagrams and expected mean squares for mixed models.

## Installation

```r
install.packages("remotes")
remotes::install_github("dkahle/cfcdae")
```

The package is pure R, so no compiler is needed on Windows or macOS, and its
dependencies are installed from CRAN automatically.

The book's [R examples](https://users.stat.umn.edu/~gary/book/RExamples/) also
use these CRAN packages:

```r
install.packages(c("nlme", "lme4", "car", "perm", "effects", "tseries", "FrF2",
                   "RLRsim", "rsm", "conf.design", "emmeans", "multcomp"))
```

## One thing to know

Loading the package runs `options(contrasts = c("contr.sum", "contr.poly"))`.
This matches the book and is required by `linear.contrast()` and
`model.effects()`, but it applies to the whole R session: every `lm()`, `aov()`
or `lmer()` fit after `library(cfcdae)` uses sum-to-zero contrasts, so
coefficients differ from those under R's default treatment contrasts.

## About this repository

cfcdae is not on CRAN; Professor Oehlert distributes it as a source tarball
from the book's page. This repository exists so that it can be installed with
one command and so that changes are tracked. All credit for the package belongs
to him; it is licensed GPL (>= 2).

The tag [`v1.4-11`](https://github.com/dkahle/cfcdae/releases/tag/v1.4-11) is
his release exactly as distributed (`cfcdae_1.4-11.tar.gz`, sha256
`f722fa9897c5d70ea1c4e97f4b9870a723c34b78200857bf439e5ee512266924`). To install
precisely that version:

```r
remotes::install_github("dkahle/cfcdae@v1.4-11")
```

Problems installing from this repository can be reported in its
[issues](https://github.com/dkahle/cfcdae/issues).
