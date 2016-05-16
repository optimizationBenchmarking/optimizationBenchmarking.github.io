---
layout: post
title:  "Evaluator GUI Now Dockerized"
date:   2016-05-16
categories: page
---

The graphical user interface ([GUI](https://github.com/optimizationBenchmarking/evaluator-gui)) of our *optimizationBenchmarking* [evaluator](https://github.com/optimizationBenchmarking/evaluator-evaluator) has now been "[dockerized](https://hub.docker.com/r/optimizationbenchmarking/evaluator-gui/)"!

Our evaluator can help researchers to quickly, conveniently, and thoroughly analyze the data obtained from experiments with optimization or machine learning algorithms. Our software is a [Java 7](https://en.wikipedia.org/wiki/Java_version_history#Java_SE_7) software which requires a [LaTeX](https://en.wikipedia.org/wiki/LaTeX) installation (such as [TeX Live](https://en.wikipedia.org/wiki/TeX_Live) or [MiKTeX](https://en.wikipedia.org/wiki/MiKTeX)), ideally including [XeLaTeX](https://en.wikipedia.org/wiki/XeTeX) and [LuaTeX](https://en.wikipedia.org/wiki/LuaTeX), [Ghostscript](https://en.wikipedia.org/wiki/Ghostscript_%28Artifex_Software_Inc%29), and [R](https://en.wikipedia.org/wiki/R_%28programming_language%29) with several Machine Learning packages. This means that installing this software in a fully functional way may be cumbersome. This problem has now been solved for our Linux users (and probably the Mac users as well, but I am not sure).

The system is now "[dockerized](https://hub.docker.com/r/optimizationbenchmarking/evaluator-gui/)"!

[Docker](http://www.docker.com/) is an application that allows you to define, publish, and run containers. Containers are something like lightweight VMs, they live as normal processes on the same kernel as the OS. Under Linux, you can install docker via

    curl -fsSL https://get.docker.com/ | sh

After doing this, you can start our container via

    docker run -t -d -p 80:8080/tcp optimizationbenchmarking/evaluator-gui

The first time you run the program, this will download the software once (and only once). Once the container is started, you can access my program by opening your browser and visiting "`localhost`". The above line of code maps port 80 to my GUI, you can replace the "80" with another port, say `8080`, if you already have a web server running. You would then browse to this port, say "`localhost:8080`".

The container contains a full installation of my system, including Tex Live, R with the required packages, and the right JDK. No further setup is needed. It is thus about 600 MB in size.

[Here](https://hub.docker.com/r/optimizationbenchmarking/evaluator-gui/) and [here](https://github.com/optimizationBenchmarking/environments-evaluator-gui/blob/master/README.md) you can find the command line options explained. This will allow you to use our system efficiently.  

If you want to uninstall the software image afterwards, use

    docker rmi -f optimizationbenchmarking/evaluator-gui
    
I hope that this makes it much easier to use our software.