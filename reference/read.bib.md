# bibtex parser

Parser for bibliography databases written in the bib format.

## Usage

``` r
read.bib(
  file = findBibFile(package),
  package = "bibtex",
  encoding = "unknown",
  header,
  footer
)
```

## Arguments

- file:

  bib file to parse. By default, the file `REFERENCES.bib` in the root
  directory of the package given by the `package` argument is used.

- package:

  package from which we want to read the bibliography. Only used if
  `file` is unspecified. Core R packages (base, datasets, graphics,
  grDevices, methods, stats, stats4, tools and utils) are treated
  specially: this package contains bibtex entries for these packages.

- encoding:

  encoding

- header:

  DEPRECATED.

- footer:

  DEPRECATED

## Value

An object of class `"bibentry"`, similar to those obtained by the
[`bibentry`](https://rdrr.io/r/utils/bibentry.html) function.

## References

Nelson H. F. Beebe. bibparse 1.04. 1999.
<http://www.math.utah.edu/~beebe/>

## Examples

``` r
## this package has a REFERENCES.bib file
bib <- read.bib(package = "bibtex")

## bibtex collects bibtex entries for R base packages
base.bib <- read.bib(package = "base")
```
