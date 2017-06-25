
<!-- README.md is generated from README.Rmd. Please edit that file -->
trickypdf
=========

Purpose
-------

At a basic level, R users have efficient tools to extract text from pdf documents. The [pdftools](https://CRAN.R-project.org/package=pdftools), and the [Rpoppler](https://CRAN.R-project.org/package=Rpoppler) packages are powerful tools.

The *trickypdf* package offers a class *PDF* to handle tricky problems that reoccurringly cause headaches when processing pdf documents with . , i.e.:

-   remove stuff outside the main text region (page headers, page numbers etc) as a preprocessing step.
-   handle multi-column layouts;
-   reconstruct lines of text, if the (OCRed) document has been scanned in tilted fashion;
-   reconstruct paragraphs.

The output will be a valid XML document, with optional document metadata. The XML output is meant to serve as the input to a Natural Language Processing (NLP) pipeline. A method to create browsable html from the xmlified pdf document is meant to assist quality checking in corpus preparation.

Installation
------------

The package relies on the pdftohtml command line utility that is part of the poppler library. On Linux, installation is easy:

``` sh
sudo apt-get install -y poppler-utils
```

On MacOS, it is recommended to use Homebrew as a package manager. To install brew, open a terminal and install Homebrew.

``` sh
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

The snippet is taken from the [Homebrew website](https://brew.sh). You can then install poppler as follows,

``` sh
brew install poppler
```

To check that poppler is installed, check the availability of the pdftohtml command line utility.

``` sh
pdftohtml -v
```

The trickypdf-package imports from a set of standard R packages that are available from CRAN using `install.packages`.

``` r
install.packages(
  pkgs = c("methods", "xml2", "pbapply", "Rpoppler", "htmltools", "markdown", "stringi", "plyr")
  )
```

Finally, trickypdf can be installed from GitHub using devtools.

``` r
install.packages("devtools") # if you have not yet installed devtools
devtools::install_github("PolMine/trickypdf")
```

Usage
-----

Contributing to package development
-----------------------------------

Please note that this project is released with a [Contributor Code of Conduct](CONDUCT.md). By participating in this project you agree to abide by its terms.
