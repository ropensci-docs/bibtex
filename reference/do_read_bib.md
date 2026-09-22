# Read the raw entries of a bib file

Parses a bib file into its entries without building
[`bibentry`](https://rdrr.io/r/utils/bibentry.html) objects. This is the
parser used by
[`read.bib`](https://docs.ropensci.org/bibtex/reference/read.bib.md),
exported for packages that process the entries differently.

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

## Value

A list with one element per entry, leaving out `@string`, `@preamble`
and `@comment` blocks. Each element is a character vector of field
values, named by field as written, with the outer braces or quotes
removed and the file's `@string` macros expanded. Its attributes are
`entry` (the entry type as written), `key` (the citation key) and
`srcref` (the line numbers from the start of the entry up to the next
entry or the end of the file). An empty file, or one holding only
comments, gives an empty list.

## Details

The parser is greatly inspired from the `bibparse` library.

## See also

[`bibentry`](https://rdrr.io/r/utils/bibentry.html)

## Examples

``` r
entries <- do_read_bib(system.file("bib", "xampl_single.bib",
  package = "bibtex"
))
attr(entries[[1]], "key")
#> [1] "article-full"
entries[[1]][["title"]]
#> [1] "The Gnats and Gnus Document Preparation System"
```
