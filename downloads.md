---
layout: default
title:  "Downloads"
categories: default
---

<h1>Downloads &amp; Installation</h1>

For using the software, you may first <a href="#down">download</a> it.
The software requires a set of other tools, which you then should <a href="#inst">install</a> in order to get everything to work smoothly.

<h2 id="down">Downloads of Java Software Version</h2>

This only holds if you want to run the `jar`s directly.
You may enjoy the {{ site.projectNameStyled }} software Java `jar` releases  in two flavors:

<ol>
<li><a href="https://github.com/optimizationBenchmarking/evaluator-gui/releases/download/{{ site.guiVersion }}/evaluatorGui.jar">evaluator/GUI</a> (Version: {{ site.guiVersion }})</li>
<li><a href="https://github.com/optimizationBenchmarking/evaluator-evaluator/releases/download/{{ site.cliVersion }}/evaluator.jar">evaluator/CLI</a> (Version: {{ site.cliVersion }})</li>
</ol>

The <a href="https://github.com/optimizationBenchmarking/evaluator-gui/releases/download/{{ site.guiVersion }}/evaluatorGui.jar">GUI</a> is a stand-alone server providing a web-based interface for managing your experimental data, creating meta data, and running the evaluator.

The <a href="https://github.com/optimizationBenchmarking/evaluator-evaluator/releases/download/{{ site.cliVersion }}/evaluator.jar">CLI</a>, i.e., the command line interface, is a only the pure evaluator component to be executed manually.

Both software come as stand-alone `jar`s and you can run them via `java -jar evaluatorGui.jar` (in case of the GUI) and `java -jar evaluator.jar` in case of the evaluator.

<h2 id="install">Installation of Java Software Version</h2>

This only holds if you want to run the `jar`s directly and do not use Docker. Otherwise, this step is irrelevant for you &ndash; if you use Docker, nothing else is required.

The runtime environment for the {{ site.projectNameStyled }} framework requires a set a [Java JDK](https://en.wikipedia.org/wiki/Java_Development_Kit), a [LaTeX](https://en.wikipedia.org/wiki/LaTeX) installation, and [`R`](https://www.r-project.org/)  with a set of pre-installed packages.

I recommend:

- [`Java 8 OpenJDK`](http://openjdk.java.net/projects/jdk8/) (Linux: install `ca-certificates-java` and `openjdk-8-jdk`)
- [`TeX Live`](http://www.tug.org/texlive/) for Linux (install: `texlive-base`, `texlive-fonts-recommended`, `texlive-luatex`, or `texlive-xetex`) or [`MiKTeX`](http://www.miktex.org/) for Windows: Make sure to install the LaTeX, XeLaTeX and LuaLaTeX components
- [`ghostscript`](http://ghostscript.com/)
- [`R`](https://www.r-project.org/) (Linux: install `libicu-dev`, `pkg-config`, `r-base=3.3.*`, and `r-base-dev=3.3.*`)

For [`R`](https://www.r-project.org/) we automatically pre-install libraries which may be needed by our software, namely

- [`apcluster`](https://cran.r-project.org/web/packages/apcluster/index.html)
- [`cluster`](https://cran.r-project.org/web/packages/cluster/index.html)
- [`fpc`](https://cran.r-project.org/web/packages/fpc/index.html)
- [`mclust`](https://cran.r-project.org/web/packages/mclust/index.html)
- [`NbClust`](https://cran.r-project.org/web/packages/NbClust/NbClust.pdf)
- [`stats`](http://stat.ethz.ch/R-manual/R-patched/library/stats/html/stats-package.html)
- [`vegan`](https://cran.r-project.org/web/packages/vegan/index.html)

Under Linux, you may copy the following text to the command line (it may ask you for your `sudo` password a few times for installing these packages, given that you have `R` already installed:

    R_params="repos=c(\"http://cran.us.r-project.org\", \"http://cran.uk.r-project.org\",  \"http://mirrors.ustc.edu.cn/CRAN\", \"http://cran.wu.ac.at/\", \"http://cran.utstat.utoronto.ca/\", \"http://cran.rstudio.com/\", \"https://cran.uni-muenster.de/\", \"http://ftp.iitm.ac.in/cran/\" ), dependencies=TRUE, clean=TRUE" &&\
    sudo Rscript -e "update.packages(ask=FALSE, ${R_params})" &&\
    sudo Rscript -e "if(!(require(\"apcluster\"))) install.packages(\"apcluster\", ${R_params})" &&\
    sudo Rscript -e "if(!(require(\"cluster\"))) install.packages(\"cluster\", ${R_params})" &&\
    sudo Rscript -e "if(!(require(\"fpc\"))) install.packages(\"fpc\", ${R_params})" &&\
    sudo Rscript -e "if(!(require(\"mclust\"))) install.packages(\"mclust\", ${R_params})" &&\
    sudo Rscript -e "if(!(require(\"NbClust\"))) install.packages(\"NbClust\", ${R_params})" &&\
    sudo Rscript -e "if(!(require(\"stats\"))) install.packages(\"stats\", ${R_params})" &&\
    sudo Rscript -e "if(!(require(\"vegan\"))) install.packages(\"vegan\", ${R_params})"
