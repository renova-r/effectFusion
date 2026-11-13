# effectFusion

Bayesian effect fusion and variable selection for categorical predictors in linear and logistic regression models.

Compatibility updates by Renova.

Version 1.1.3.9002 is a platform compatibility patch: the BLAS/LAPACK calls now use R's canonical prototypes with the hidden Fortran character-length arguments (`FCONE`, `-DUSE_FC_LEN_T`), which fixes the WebAssembly link errors, and the boolean-multiplication in `src/Logit.h` is written with `&&`, which removes the Windows compiler warning. Numerical results are unchanged.

Version 1.1.3.9001 removes the stale optional `Date` field from `DESCRIPTION` and makes two other changes. In `man/effectFusion.Rd` the nested `\describe` lists in the `\value` section were restructured so that they are well-formed. In `src/MatrixFrame.h` the include of `R_ext/PrtUtil.h` was replaced by `R.h`. No R function was changed.

## Install

From R-universe:

```r
install.packages("effectFusion", repos = c(
  Renova = "https://renova-r.r-universe.dev",
  CRAN = "https://cloud.r-project.org"
))
```

Or the exact release tag:

```r
install.packages("remotes")
remotes::install_github("renova-r/effectFusion@renova-1.1.3.9002")
```

[Release notes](NEWS.md) · [Renova package directory](https://github.com/renova-r/revival-catalog)

effectFusion was written by Daniela Pauger, Magdalena Leitner (maintainer), Helga Wagner and Gertraud Malsiner-Walli, with contributions by Nicholas G. Polson, James G. Scott, Jesse Windle and Bettina Grün. The Polya-Gamma sampling code comes from the R package BayesLogit (Polson, Scott and Windle) and keeps its copyright notices. License: GPL-3 (see [COPYING](COPYING)).
