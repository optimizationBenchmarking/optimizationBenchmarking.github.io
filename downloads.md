---
layout: default
title:  "Downloads"
categories: default
---

<h1>Downloads &amp; Installation</h1>

For using the software, you may first <a href="#down">download</a> it. The software requires a set of other tools, which you then should <a href="#inst">install</a> in order to get everything to work smoothly. Alternatively, if you are using Linux, MacOS, or Windows (on a 64 bit system), you can also use the <a href="#docker">dockerized</a> version of the GUI. The latter is recommended, as it only requires you to install Docker and then you are ready to go! 

<h2 id="docker">Dockerized Version: Only Install Docker, Nothing Else!</h2>

The graphical user interface ([GUI](https://github.com/optimizationBenchmarking/evaluator-gui)) of our {{ site.projectNameStyled }} [evaluator](https://github.com/optimizationBenchmarking/evaluator-evaluator) has <a href="{ site.baseurl }}/page/2016/05/16/dockerized.html">now</a> been "[dockerized](https://hub.docker.com/r/optimizationbenchmarking/evaluator-gui/)". [Docker](http://www.docker.com/) is an application that allows you to define, publish, and run containers. Containers are something like lightweight VMs, they live as normal processes on the same kernel as the OS under Linux and as small Virtual Box VMs under Windows and Mac OS. Docker can be installed following the guidelines below:

* for [Linux](https://docs.docker.com/linux/step_one/), you can run  `curl -fsSL https://get.docker.com/ | sh` on your command line and everything is done automatically (if you have `curl` installed, which is normally the case),
* for [Windows](https://docs.docker.com/windows/step_one/)
* for [Mac OS](https://docs.docker.com/mac/step_one/)

After doing this, you can start our container by typing the following command into a normal terminal (Linux), the *Docker Quickstart Terminal* (Mac OS), or the *Docker Toolbox Terminal* (Windows):

    docker run -t -d -p 9999:8080/tcp optimizationbenchmarking/evaluator-gui

The first time you run the program, this will download the software once (and only once). Once the container is started, you can access it with your browser at address

- [http://localhost:9999](http://localhost:9999) under Linux or
- `http://<dockerIP>:9999` under Windows and Mac OS, where `dockerIP` is the IP address of your Docker container. This address is displayed when you run the container. You can also obtain it with the command `docker-machine ip default`.

The container contains a full installation of my system, including the [`Java 8 OpenJDK`](http://openjdk.java.net/projects/jdk8/), [`TeX Live`](http://www.tug.org/texlive/), [`R`](https://www.r-project.org/), the needed `R` packages, and [`ghostscript`](http://ghostscript.com/). No further setup is needed. It is thus about 600 MB in size.

[Here](https://hub.docker.com/r/optimizationbenchmarking/evaluator-gui/) and [here](https://github.com/optimizationBenchmarking/environments-evaluator-gui/blob/master/README.md) you can find the command line options explained. This will allow you to use our system efficiently.

<h2 id="down">Downloads of Java Software Version</h2>

This only holds if you want to run the `jar`s directly and do not use Docker. Otherwise, this step is irrelevant for you &ndash; if you use Docker, nothing else is required.

So if you want to use the `jar`s directly, maybe because you already have R and Java and TeX Live installed and want to save disk space: You may enjoy the {{ site.projectNameStyled }} software Java `jar` releases  in two flavors:

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


<h2>Documentation</h2>

There are currently two slide sets with documentation about our system:

- <a href="https://circleci.com/api/v1/project/optimizationBenchmarking/documentation-intro-slides/latest/artifacts/0/$CIRCLE_ARTIFACTS/intro-slides.pdf?branch=master">a general introduction</a>
- <a href="https://circleci.com/api/v1/project/optimizationBenchmarking/documentation-technical-intro-slides/latest/artifacts/0/$CIRCLE_ARTIFACTS/intro-slides.pdf?branch=master">a technical introduction</a>