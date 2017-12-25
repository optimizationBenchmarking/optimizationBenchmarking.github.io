---
layout: default
title: optimizationBenchmarking.org
permalink: /
---

# Introduction
This is the main website of the {{ site.projectNameStyled }} framework, a (dockerized) `Java 1.7` software designed to make the evaluation, benchmarking, and comparison of [optimization](http://en.wikipedia.org/wiki/Mathematical_optimization) or [Machine Learning](http://en.wikipedia.org/wiki/Machine_learning) algorithms easier. This software is developed at the Institute of Applied Optimization [(IAO)](http://iao.hfuu.edu.cn) at Hefei Universit in Hefei, Anhui, China. This software can load log files created by (experiments with) an optimization or Machine Learning algorithm implementation, evaluate how the implementation has progressed over time, and compare its performance to other algorithms (or implementations) -- over several different benchmark cases. It can create reports in [LaTeX](http://en.wikipedia.org/wiki/LaTeX) (ready for publication) or [XHTML](http://en.wikipedia.org/wiki/XHTML) formats or export its findings in text files which may later be loaded by other applications. It does not make any requirements regarding the implementation of the algorithms under investigation (also not regarding the programming language) and does not require any programming for your side! It has a convenient GUI. A short set of introduction slides about this project can be found <a href="{{ site.baseurl }}/introSlides.html">here</a>.

## Workshop!
We jointly organize the [International Workshop on Benchmarking of Computational Intelligence Algorithms (BOCIA)](http://iao.hfuu.edu.cn/bocia18) at the Tenth International Conference on Advanced Computational Intelligence (ICACI 2018) on March 29-31, 2018 in Xiamen, China. The paper submission deadline is November 15, 2017. Here is the CfP.

## Quick Start
If you want to directly run our software and see the examples, you can use its [dockerized version](https://hub.docker.com/r/optimizationbenchmarking/evaluator-gui/). Simply perform the following steps:

1. Install [Docker](http://www.docker.com) following the instructions for [Linux](https://docs.docker.com/linux/step_one/), [Windows](https://docs.docker.com/windows/step_one/), or [MacOS](https://docs.docker.com/mac/step_one/).
2. Open a normal terminal (Linux), the *Docker Quickstart Terminal* (Mac OS), or the *Docker Toolbox Terminal* (Windows).
3. Type in <code class="highlighter-rouge" style="white-space:nowrap">docker&nbsp;run&nbsp;-t&nbsp;-i&nbsp;-p&nbsp;9999:8080/tcp&nbsp;optimizationbenchmarking/evaluator-gui</code> and hit return. Only the first time you do that, it downloads our software. This may take some time, as the software is a 600 MB package. After the download, the software will start. 
4. Browse to
  - [`http://localhost:9999`](http://localhost:9999) under Linux
  - `http://<dockerIP>:9999` under Windows and Mac OS, where `dockerIP` is the IP address of your Docker container. This address is displayed when you run the container. You can also obtain it with the command `docker-machine ip default`.
5. Enjoy the web-based GUI of our software, which looks quite similar to this web site.

## Posts
<ul class="posts">
{% for post in site.posts %}
<li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></li>
{% endfor %}
</ul>

## Workflow
The {{ site.projectNameStyled }} framework prescribes the following work flow, which is discussed
in more detail in [this set of slides]({{ site.baseurl }}/introSlides.html):

1. *Algorithm Implementation:* You implement your algorithm. Do it in a way so that you can generate log files containing rows such as (`passed runtime`, `best solution quality so far`) for each run (execution) of your algorithm. You are free to use any programming language and run it in any environment you want. We don't care about that, we just want the text files you have generated.
2. *Choose Benchmark Instances:* Choose a set of (well-known) problem instances to apply your algorithm to.
3. *Experiments:* Well, run your algorithm, i.e., apply it a few times to each benchmark instance. You get the log files. Actually, you may want to do this several times with different parameter settings of your algorithm. Or maybe for different algorithms, so you have comparison data.
4. *Use Evaluator:* Now, you can use our evaluator component to find our how good your method works! For this, you can define the *dimensions* you have measured (such as runtime and solution quality), the features of your benchmark instances (such as number of cities in a Traveling Salesman Problem or the scale and symmetry of a numerical problem), the parameter settings of your algorithm (such as population size of an EA), the information you want to get (ECDF? performance over time?), and how you want to get it (LaTeX, optimized for IEEE Transactions, ACM, or Springer LNCS? or maybe XHTML for the web?). Our evaluator will create the report with the desired information in the desired format.
5. By interpreting the report and advanced statistics presented to you, you can get a deeper insight into your algorithm's performance as well as into the features and hardness of the benchmark instances you used. You can also directly use building blocks from the generated reports in your publications. 