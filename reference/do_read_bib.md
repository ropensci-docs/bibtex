# convenience wrapper around .External call

This is a convenience function for packages that do need to call the
internal functionality of
[`read.bib`](https://docs.ropensci.org/bibtex/reference/read.bib.md) but
does different processing. This is a simple wrapper around the
`.External` code used by
[`read.bib`](https://docs.ropensci.org/bibtex/reference/read.bib.md)

## Usage

``` r
do_read_bib(file, encoding = "unknown", srcfile)
```

## Arguments

- file:

  file name

- encoding:

  encoding

- srcfile:

  Deprecated

## Details

The parser is greatly inspired from the `bibparse` library.

## See also

[`bibentry`](https://rdrr.io/r/utils/bibentry.html)
