---
layout: post
title:  "TSP Suite Example: The Traveling Salesman Problem"
date:   2016-05-10
categories: page
---

We added an [new example data set]({{ site.rooturl }}/documentation-examples/data/tspSuite)] from several algorithms solving the Traveling Salesman Problem ([TSP](https://en.wikipedia.org/wiki/Travelling_salesman_problem)) gathered with the [TSP Suite](https://github.com/optimizationBenchmarking/tspSuite). The TSP Suite&nbsp;[1] is the direct predecessor of the  *optimizationBenchmarking.org* framework. Here we conduct experiments based on the 68 smallest-scale symmetric benchmark instances from the [TSPLib](www.iwr.uni-heidelberg.de/groups/comopt/software/TSPLIB95/) benchmark set&nbsp;[2].


The [TSP](https://en.wikipedia.org/wiki/Travelling_salesman_problem) is maybe the oldest and most well-known combinatorial optimization problem. Given are *n* cities. A salesman starts at one of these cities. He wants to visit all other cities (each exactly once) and then return to his origin. The question for the shortest tour that he can take to realize this travel is [NP-hard](https://en.wikipedia.org/wiki/NP-hard) and the best exact algorithms for solving this problem need a runtime exponential in *n* to find the best-possible solution in the worst case.

As benchmark problems for our TSP example, we use some instances from the well-known [TSPLib](www.iwr.uni-heidelberg.de/groups/comopt/software/TSPLIB95/)&nbsp;[2]. We pick the 68 smallest-scale instances from 110 symmetric instances to run out experiments.

Here we investigate twelve *anytime optimization* methods for the TSP, i.e., algorithms that can step-wise improve their best guess of the solution. They can provide an approximate solution at any time. Among the tested algorithms, you can find 11 [metaheuristics](https://en.wikipedia.org/wiki/Metaheuristic) and one [branch and bound](https://en.wikipedia.org/wiki/Branch_and_bound) algorithm.

## References
1. Thomas Weise, Raymond Chiong, Ke Tang, Jörg Lässig, Shigeyoshi Tsutsui, Wenxiang Chen, Zbigniew Michalewicz, and Xin Yao. Benchmarking Optimization Algorithms: An Open Source Framework for the Traveling Salesman Problem. *IEEE Computational Intelligence Magazine (CIM)*. 9(3):40-52. August 2014. Piscataway, NJ, USA: IEEE Computational Intelligence Society. [pdf](http://www.it-weise.de/research/publications/WCTLTCMY2014BOAAOSFFTTSP/WCTLTCMY2014BOAAOSFFTTSP.pdf), doi:[10.1109/MCI.2014.2326101](http://dx.doi.org/10.1109/MCI.2014.2326101). Featured article and selected paper at the website of the IEEE Computational Intelligence Society (http://cis.ieee.org/).
2. Gerhard Reinelt. TSPLIB - A Traveling Salesman Problem Library. *ORSA Journal on Computing*. 3(4):376-384. 1991. Operations Research Society of America (ORSA). doi:[10.1287/ijoc.3.4.376](10.1287/ijoc.3.4.376)