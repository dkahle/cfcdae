# cfcdae 1.4-11.1

Changes made in this repository (by David Kahle) relative to Gary Oehlert's
cfcdae 1.4-11, which is preserved unmodified at the tag `v1.4-11`. Each change
is also marked with a comment at the place it was made.

## Bug fixes

* `compare.to.control()` and `compare.to.best()` no longer fail on `lmer()`
  fits with "'df' is not an integer". `qdunnett()` now rounds `errordf` after
  verifying that it is an integer to within 1e-7; Kenward-Roger degrees of
  freedom arrive with floating-point noise (e.g. 51.0000000000002) and current
  versions of mvtnorm require an exact integer. Results are unchanged for every
  input that previously worked (#1).
* `sample.size.f.test()` now rejects every non-integer `ngrps`. A misplaced
  parenthesis let values that round up, such as 3.7, through; they were then
  silently truncated (#2).

## Package metadata

* `DESCRIPTION`: Gary Oehlert remains author and maintainer. David Kahle is
  added as a contributor, with a note that he maintains this GitHub
  distribution; `URL` now points to the book's web page; and the `Packaged`,
  `Author` and `Maintainer` fields, which R regenerates whenever the package is
  built, were removed from the source file.

## Known problems

* `compare.to.control()` and `compare.to.best()` stop with "errordf must be a
  positive integer" when the Kenward-Roger degrees of freedom are genuinely
  fractional, as they usually are for unbalanced mixed models (#3).
* The contrast-based functions do not work on `nlme::lme` fits. Use
  `lme4::lmer()` instead (#4).

# cfcdae 1.4-11

Gary Oehlert's release, as distributed from
<https://users.stat.umn.edu/~gary/Book.html>.
