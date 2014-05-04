openxlsx
========
This [R](http://www.r-project.org/) package simplifies the
creation of `.xlsx` files by providing 
a high level interface to writing, styling and editing
worksheets. Through the use of
[`Rcpp`](http://cran.r-project.org/web/packages/Rcpp/), 
read/write times are comparable to the
[`xlsx`](http://cran.r-project.org/web/packages/xlsx/index.html)
and
[`XLConnect`](http://cran.r-project.org/web/packages/XLConnect)
packages with the added benefit of removing the dependency on
Java. 

## Install


### Stable version
Current stable version is available on
[CRAN](http://cran.r-project.org/), therefore from 
inside R
```r
install.packages("openxlsx", dependencies=TRUE)
```

### Development version
Development version can be installed via GitHub. Before that, you
need to setup:

1. Rtools (Windows only), available
[here](http://cran.r-project.org/bin/windows/Rtools/). In the
installation process, set up `PATH` to include Rtools directories.
2. `Rcpp` and `devtools` 
```R
install.packages(c("Rcpp", "devtools"), dependencies=TRUE)
```

Then:
```r
install_github("openxlsx", "awalker89")
```
On *some Unix platform* `install_github` has been [reported](https://github.com/hadley/devtools/issues/467) not to
work as expected. A handy workaround, in the meantime, could be the following
simple bash script (eg named `r_install_github`):

```bash
#!/bin/bash
# usage (eg):
#    r_install_github devtools hadley

cd /tmp && \
rm -rf R_install_github && \
mkdir R_install_github  && \
cd R_install_github && \
wget https://github.com/$2/$1/archive/master.zip && \
unzip master.zip
R CMD build $1-master && \
R CMD INSTALL $1*.tar.gz && \
cd /tmp && \
rm -rf R_install_github
```

and to install `openxlsx` (after giving execution permissions and
putting it in a `PATH` directory):
```bash
r_install_github openxlsx awalker89
```

## Bug/feature request
Thanks, [here](https://github.com/awalker89/openxlsx/issues). 

## News
[Here](https://raw.githubusercontent.com/awalker89/openxlsx/master/NEWS). 

## Authors and Contributors
A list is automagically maintained
[here](https://github.com/awalker89/openxlsx/graphs/contributors). 