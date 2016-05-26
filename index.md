---
layout: default
title: Optimization Benchmarking
permalink: /
---

# Introduction
This is the main website of the *optimizationBenchmarking.org* framework, a `Java 1.7` software designed to make the evaluation, benchmarking, and comparison of [optimization](http://en.wikipedia.org/wiki/Mathematical_optimization) or [Machine Learning](http://en.wikipedia.org/wiki/Machine_learning) algorithms easier. This software  can load log files created by (experiments with) an optimization or Machine Learning algorithm implementation, evaluate how the implementation has progressed over time, and compare its performance to other algorithms (or implementations) -- over several different benchmark cases. It can create reports in [LaTeX](http://en.wikipedia.org/wiki/LaTeX) (ready for publication) or [XHTML](http://en.wikipedia.org/wiki/XHTML) formats or export its findings in text files which may later be loaded by other applications. A short set of introduction slides about this project can be found <a href="{{ site.baseurl }}/introSlides.html">here</a>.

## Posts
<ul class="posts">
{% for post in site.posts %}
<li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></li>
{% endfor %}
</ul>

## Workflow
The *optimizationBenchmarking.org* framework prescribes the following work flow, which is discussed
in more detail in [this set of slides](https://circleci.com/api/v1/project/optimizationBenchmarking/documentation-intro-slides/latest/artifacts/0/$CIRCLE_ARTIFACTS/intro-slides.pdf?branch=master):

1. *Algorithm Implementation:* You implement your algorithm. Do it in a way so that you can generate log files containing rows such as (`passed runtime`, `best solution quality so far`) for each run (execution) of your algorithm.
2. *Choose Benchmark Instances:* Choose a set of (well-known) problem instances to apply your algorithm to.
3. *Experiments:* Well, run your algorithm, i.e., apply it a few times to each benchmark instance. You get the log files. Actually, you may want to do this several times with different parameter settings of your algorithm. Or maybe for different algorithms, so you have comparison data.
4. *Use Evaluator:* Now, you can use our evaluator component to find our how good your method works! For this, you can define the *dimensions* you have measured (such as runtime and solution quality), the features of your benchmark instances (such as number of cities in a TSP), the parameter settings  of your algorithm (such as population size of an EA), information you want to get (ECDF? performance over time?), and how you want to get it (LaTeX, optimized for IEEE Transactions, ACM, or Springer LNCS? or maybe XHTML for the web?). Our evaluator will create the report with the desired information in the desired format.