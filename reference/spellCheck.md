# Find and Replace

This is a helper function for finding and replacing from lexicons like
the event list. The lexicons are all named lists where the name is the
text to replace and the value what it should be replaced with It uses
fuzzy find and replace to account for spelling errors

## Usage

``` r
spellCheck(pattern, replacement, x, fixed = FALSE)
```

## Arguments

- pattern:

  the pattern to look for

- replacement:

  the pattern replaceme with

- x:

  the target string

- fixed:

  whether the pattern is regex or not. Default not.

## Value

This returns a character vector

## Examples

``` r
L <- tolower(stringr::str_split(HistolType(),"\\|"))
```
