FROM openanalytics/r-base

LABEL maintainer="pokyah"

RUN export DEBIAN_FRONTEND=noninteractive; apt-get -y update \
  && apt-get install -y gdal-bin \
	git-core \
	libcurl4-openssl-dev \
	libgdal-dev \
	libgeos-dev \
	libpng-dev \
	libproj-dev \
	libssl-dev \
	libudunits2-dev \
	libxml2-dev \
	make \
	pandoc \
	pandoc-citeproc

RUN ["install2.r", "assertthat", "backports", "base64enc", "BBmisc", "bindr", "bindrcpp", "checkmate", "chron", "class", "classInt", "colorspace", "crosstalk", "curl", "data.table", "DBI", "devtools", "digest", "dplyr", "e1071", "evaluate", "FNN", "formatR", "futile.logger", "futile.options", "ggplot2", "glue", "gtable", "htmltools", "htmlwidgets", "httpuv", "httr", "jsonlite", "knitr", "labeling", "lambda.r", "later", "lattice", "lazyeval", "leaflet", "learnr", "magrittr", "markdown", "Matrix", "memoise", "mime", "mlr", "munsell", "nnet", "parallelMap", "ParamHelpers", "pillar", "pkgconfig", "plyr", "png", "promises", "purrr", "R6", "raster", "RColorBrewer", "Rcpp", "remotes", "rgdal", "rjson", "rmarkdown", "rprojroot", "scales", "semver", "sf", "shiny", "sp", "spData", "stringi", "stringr", "survival", "tibble", "udunits2", "units", "withr", "XML", "xtable", "yaml", "rgeos", "elevatr", "rnaturalearth"]

RUN ["installGithub.r", "Nowosad/spDataLarge@b0cceccd1549b0944740edc4031ba42d00024ea1", "pokyah/agrometAPI@c87c078449be2929cecfc9e3fe6483554817a397", "richfitz/stevedore@29ffb67985e97c468d283428e4f1e203543d147e", "rstudio/fontawesome@ba97af5b52615627e1284e7c50c128a91881a16c", "tidyverse/rlang@6517f964f6982d85ff170ccdda859463c55cc006", "ropensci/rnaturalearthhires@7a3f0fc8d8d690fae044dd01eb2f14d3a75c92ed"]


# copy the app to the image
RUN mkdir /root/spagrometeor-tuto/
COPY app /root/spagrometeor-tuto/


EXPOSE 3838


CMD ["R", "--vanilla", "-e", "rmarkdown::run(file = \"/root/spagrometeor-tuto/tuto.Rmd\", shiny_args = list(port=3838))"]
