---
output: github_document
---

<!-- README.md is generated from README.Rmd. Please edit that file -->


# annotatedMM

<!-- badges: start -->
<!-- badges: end -->

The `annotatedMM` package provides an interface to work with our "annotated" Matrix Market exchange format which we call "AMM".

The Matrix Market exchange format (variously referred to as MM, MTX or MEX) are formats typically used to represent sparse matrices in an efficient manner (since zero matrix positions are not reported).

One major drawback of the format however is that it does not describe a way to store useful metadata such as row or column names.

Our "annotated" MM format (AMM) makes use of comment lines (those typically at the top of MM files starting with `'%'`) - to store this metadata.

Since comment lines are used, any software not understanding our metadata injection formats will simply ignore these lines which may or may not be desired, but at the very least, our "AMM" file is a valid "MM" file.

Metadata stored by default includes row and column names of sparse matrices (dGCMatrix, sparseMatrix etc - formats supported by `Matrix::writeMM()` and `Matrix::readMM()`).

It is planned but not currently supported by `annotatedMM` to allow users to inject custom metadata. Some careful design of a metadata format specification will be required before this is implemented.

Row and column metadata lines are formatted as follows:

```
%ROWNAMES<tab>Row1<tab>Row2<tab>...
%COLNAMES<tab>Sample1<tab>Sample2<tab>...
```

Note: `<tab` in the above used to represent actual tabstops.


## Installation

You can install the released version of annotatedMM from [CRAN](https://CRAN.R-project.org) with:

``` r
install.packages("annotatedMM")
```

## Example

This is a basic example which shows you how to solve a common problem:


```r
library(annotatedMM)
#> Error in library(annotatedMM): there is no package called 'annotatedMM'
## basic example code
```

What is special about using `README.Rmd` instead of just `README.md`? You can include R chunks like so:


```r
summary(cars)
#>      speed           dist       
#>  Min.   : 4.0   Min.   :  2.00  
#>  1st Qu.:12.0   1st Qu.: 26.00  
#>  Median :15.0   Median : 36.00  
#>  Mean   :15.4   Mean   : 42.98  
#>  3rd Qu.:19.0   3rd Qu.: 56.00  
#>  Max.   :25.0   Max.   :120.00
```

You'll still need to render `README.Rmd` regularly, to keep `README.md` up-to-date.

You can also embed plots, for example:

<img src="man/figures/README-pressure-1.png" title="plot of chunk pressure" alt="plot of chunk pressure" width="100%" />

In that case, don't forget to commit and push the resulting figure files, so they display on GitHub!
