This package contains the interactive presentation I'll give at [FOSS4GBXL2018](https://2018.foss4g.be/)

* you can run it online without any installation on https://pokyah.shinyapps.io/foss4GBXL2018
* or you can run it on your own computer by installing it using `devtools` :

```r
install.packages("learnr") # library required for interactive tutorials
devtools::install_github("pokyah/FOSS4GBXL2018", ref = "master") # this package
packrat::restore() # install all the R-packages required for this tuto using packrat
learnr::run_tutorial("presentation", package = "FOSS4GBXL2018") # launch the tutorial
```

The tutorial makes a call to the agrometAPI. In order to use it, you must provide your own
user token in your `.Renviron` file. 

The package provides a limited cached extraction from the API to allow you to play with the data.

The `example.Renviron` located at the root of this repository show you the name of the environment variable you must use in order to allow the `agrometAPI` package to read and retrieve your token.
