# Generate a Bibtex File from Package Citations

Generates a Bibtex file from a
[`bibentry`](https://rdrr.io/r/utils/bibentry.html) object or a list of
packages. It is useful for adding relevant citations in Sweave
documents.

## Usage

``` r
write.bib(entry, file = "Rpackages.bib", append = FALSE, verbose = TRUE)
```

## Arguments

- entry:

  a [`bibentry`](https://rdrr.io/r/utils/bibentry.html) object or a
  character vector of package names.

- file:

  output Bibtex file.

- append:

  logical. If `TRUE` content is appended to the file.

- verbose:

  a logical to toggle verbosity.

## Value

the list of Bibtex objects – invisibly.

## References

*\[R\] Creating bibtex file of all installed packages?* Achim Zeileis.
R-help mailing list.

## Author

Renaud Gaujoux, based on the function `Rpackages.bib` from Achim Zeileis
(see *References*).

## Examples

``` r
tmp <- tempfile(fileext = ".bib")
write.bib(c("bibtex", "utils", "tools"), file = tmp)
#> Converted 3 of 3 package citations to BibTeX
#> Writing 3 Bibtex entries ... 
#> OK
#> Results written to file '/tmp/RtmpqbVxAT/file5af740c06ed.bib'
bibs <- read.bib(tmp)

tmp2 <- tempfile(fileext = ".bib")
write.bib(bibs, tmp2)
#> Writing 3 Bibtex entries ... 
#> OK
#> Results written to file '/tmp/RtmpqbVxAT/file5af5d7dcc8c.bib'
unname(tools::md5sum(tmp) == tools::md5sum(tmp2))
#> [1] TRUE

unlink(c(tmp, tmp2))
```
