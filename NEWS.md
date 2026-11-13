# effectFusion 1.1.3.9002

Platform compatibility patch to Renova release 1.1.3.9001, which is based on CRAN effectFusion 1.1.3 (published 2021-10-13).

- `src/MatrixFrame.h`, `src/Matrix.h`: the hand-written double-precision BLAS/LAPACK prototypes were removed; `<R_ext/BLAS.h>` and `<R_ext/Lapack.h>` (with `<Rconfig.h>` and an empty fallback `FCONE`) now declare them, so the hidden `FC_LEN_T` character-length arguments are passed. WebAssembly checks function signatures at link time and rejected the old prototypes.
- `src/Matrix.cpp`, `src/MatrixFrame.cpp`: one `FCONE` per character argument was appended to the 10 calls (dsyevd, dgesvd, dgesdd, dgemm, dsyr2k, dtrmm, dtrsm, dsyrk, dposv, dpotrf). Called routines and numeric arguments are unchanged.
- `src/Makevars`: `-DUSE_FC_LEN_T` added to `PKG_CPPFLAGS`.
- `src/Logit.h`: `ok *= check[i] = ...` (flagged by `-Wint-in-bool-context` on Windows) became `check[0] = ...; check[1] = ...; ok = ok && check[0] && check[1];`; results and messages are identical.
- No R code, `NAMESPACE`, help page or data changed.
- `DESCRIPTION`: `Version` set to `1.1.3.9002`. `README.md` and `NEWS.md` updated.

# effectFusion 1.1.3.9001

Renova release, based on CRAN effectFusion 1.1.3 (published 2021-10-13).

- `DESCRIPTION`: the stale optional `Date: 2021-10-13` field was removed.
- `man/effectFusion.Rd`: nested `\describe`/`\item{}` blocks in the `\value` section for `fit`, `fit_burnin`, `refit` and `data` were restructured into well-formed lists; wording is unchanged.
- `src/MatrixFrame.h`: `#include <R_ext/PrtUtil.h>` replaced by `#include <R.h>`. No R function was changed.
- `DESCRIPTION`: `Version` set to `1.1.3.9001`; "Compatibility updates by Renova." appended to `Description`.
- The stale `MD5` file was removed. `COPYING` (license text), `README.md`, `NEWS.md` and `.Rbuildignore` were added.
