# Generate a Bibtex File from Package Citations

Generates a Bibtex file from a list of packages or all the installed
packages. It is useful for adding relevant citations in Sweave
documents.

## Usage

``` r
write.bib(entry, file = "Rpackages.bib", append = FALSE, verbose = TRUE)
```

## Arguments

- entry:

  a [`bibentry`](https://rdrr.io/r/utils/bibentry.html) object or a
  character vector of package names. If `NULL`, then the list of all
  installed packages is used.

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

write.bib(c("bibtex", "utils", "tools"), file = "references")
#> Converted 3 of 3 package citations to BibTeX
#> Writing 3 Bibtex entries ... 
#> OK
#> Results written to file 'references.bib'
bibs <- read.bib("references.bib")
write.bib(bibs, "references2.bib")
#> Writing 3 Bibtex entries ... 
#> OK
#> Results written to file 'references2.bib'
md5 <- tools::md5sum(c("references.bib", "references2.bib"))
md5[1] == md5[2]
#> references.bib 
#>           TRUE 
```
