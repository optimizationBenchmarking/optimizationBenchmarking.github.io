---
layout: default
title: optimizationBenchmarking.org
permalink: /
---

# Introduction
This is a website dedicated to the benchmarking of optimization algorithms.
It was the main website of the {{ site.projectNameStyled }} framework, a `Java 1.7` software designed to make the evaluation, benchmarking, and comparison of [optimization](http://en.wikipedia.org/wiki/Mathematical_optimization) or [Machine Learning](http://en.wikipedia.org/wiki/Machine_learning) algorithms easier.
This software was developed during a research project at Hefei Universit in Hefei, Anhui, China until about 2020.
*It is no longer under active development.*

Still, it's source code is still available.
This software can load log files created by (experiments with) an optimization or Machine Learning algorithm implementation, evaluate how the implementation has progressed over time, and compare its performance to other algorithms (or implementations) -- over several different benchmark cases.
It can create reports in [LaTeX](http://en.wikipedia.org/wiki/LaTeX) (ready for publication) or [XHTML](http://en.wikipedia.org/wiki/XHTML) formats or export its findings in text files which may later be loaded by other applications. It does not make any requirements regarding the implementation of the algorithms under investigation (also not regarding the programming language) and does not require any programming for your side!
It has a convenient GUI.

In the past, a dockerized version was available.
But since dockerhub closed repositories of organizations, this configuration-free method of launching the software is gone.

## Workflow
The {{ site.projectNameStyled }} framework prescribes the following work flow:

1. *Algorithm Implementation:* You implement your algorithm. Do it in a way so that you can generate log files containing rows such as (`passed runtime`, `best solution quality so far`) for each run (execution) of your algorithm. You are free to use any programming language and run it in any environment you want. We don't care about that, we just want the text files you have generated.
2. *Choose Benchmark Instances:* Choose a set of (well-known) problem instances to apply your algorithm to.
3. *Experiments:* Well, run your algorithm, i.e., apply it a few times to each benchmark instance. You get the log files. Actually, you may want to do this several times with different parameter settings of your algorithm. Or maybe for different algorithms, so you have comparison data.
4. *Use Evaluator:* Now, you can use our evaluator component to find our how good your method works! For this, you can define the *dimensions* you have measured (such as runtime and solution quality), the features of your benchmark instances (such as number of cities in a Traveling Salesman Problem or the scale and symmetry of a numerical problem), the parameter settings of your algorithm (such as population size of an EA), the information you want to get (ECDF? performance over time?), and how you want to get it (LaTeX, optimized for IEEE Transactions, ACM, or Springer LNCS? or maybe XHTML for the web?). Our evaluator will create the report with the desired information in the desired format.
5. By interpreting the report and advanced statistics presented to you, you can get a deeper insight into your algorithm's performance as well as into the features and hardness of the benchmark instances you used. You can also directly use building blocks from the generated reports in your publications. 
