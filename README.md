We're please to anounce the first CRAN release of pacman v. 0.2.0.  pacman is the combined work of [Dason Kurkiewicz](https://github.com/Dasonk) & [Tyler Rinker](https://trinkerrstuff.wordpress.com/about/).  

<img src="https://github.com/trinker/pacman/raw/master/inst/pacman_logo/r_pacman.png" width="30%">

[pacman](https://github.com/trinker/pacman) is an R package management tool that combines the functionality of base library related functions into intuitively named functions. This package is ideally added to .Rprofile to increase workflow by reducing time recalling obscurely named functions, reducing code and integrating functionality of base functions to simultaneously perform multiple actions.



## Installing pacman


```r
install.packages("pacman")

## May need the following if binaries haven't been built yet:
install.packages("pacman", type="source")
```

Or install from GitHub via devtools:


```r
devtools::install_github("trinker/pacman")
```

As this is the first release we expect that there are kinks that need to be worked out.  We appreciate [pull requests](https://github.com/trinker/pacman/) and [issue reports ](https://github.com/trinker/pacman/issues).  

## Examples

Here are some of the functionalities the pacman authors tend to use most often:

### Installing and Loading    

`p_load` is a general use tool that can install, load, and update packages. For example, many blog posts begin coding with this sort of package call:


```r
packs <- c("XML", "devtools", "RCurl", "fakePackage", "SPSSemulate")
success <- suppressWarnings(sapply(packs, require, character.only = TRUE))
install.packages(names(success)[!success])
sapply(names(success)[!success], require, character.only = TRUE)
```

With pacman this call can be reduced to:


```r
pacman::p_load(XML, devtools, RCurl, fakePackage, SPSSemulate)
```


### Installing Temporarily

`p_temp` enables the user to temporarily install a package.  This allows a session-only install for testing out a single package without muddying the user's library.  


```r
p_temp(aprof)
```


### Package Functions & Data 


```r
p_functions(pacman)
p_funs(pacman, all=TRUE)
p_data(lattice)
```

## Vignettes

Check out pacman's vignettes:

- [HTML Vignette: Introduction to pacman](http://trinker.github.io/pacman/vignettes/Introduction_to_pacman.html)      
- [pacman Functions: Quick Reference](http://trinker.github.io/pacman_dev/vignettes/pacman_functions_quick_reference.html) 
