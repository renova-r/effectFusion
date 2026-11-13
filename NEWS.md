# effectFusion 1.1.3.9001

Renova release, based on CRAN effectFusion 1.1.3 (published 2021-10-13).

- `DESCRIPTION`: the stale optional `Date: 2021-10-13` field was removed.
- `man/effectFusion.Rd`: nested `\describe`/`\item{}` blocks in the `\value` section for `fit`, `fit_burnin`, `refit` and `data` were restructured into well-formed lists; wording is unchanged.
- `src/MatrixFrame.h`: `#include <R_ext/PrtUtil.h>` replaced by `#include <R.h>`. No R function was changed.
- `DESCRIPTION`: `Version` set to `1.1.3.9001`; "Compatibility updates by Renova." appended to `Description`.
- The stale `MD5` file was removed. `COPYING` (license text), `README.md`, `NEWS.md` and `.Rbuildignore` were added.
