---
layout: default
title:  "Downloads"
categories: default
---

The optimization benchmarking software comes in two flavors:

<ol>
<li><a href="https://github.com/optimizationBenchmarking/evaluator-gui/releases/download/{{ site.guiVersion }}/evaluatorGui.jar">evaluator/GUI</a> (Version: {{ site.guiVersion }})</li>
<li><a href="https://github.com/optimizationBenchmarking/evaluator-evaluator/releases/download/{{ site.cliVersion }}/evaluator.jar">evaluator/CLI</a> (Version: {{ site.cliVersion }})</li>
</ol>

The <a href="https://github.com/optimizationBenchmarking/evaluator-gui/releases/download/{{ site.guiVersion }}/evaluatorGui.jar">GUI</a> is a stand-alone server providing a web-based interface for managing your experimental data, creating meta data, and running the evaluator.

The <a href="https://github.com/optimizationBenchmarking/evaluator-evaluator/releases/download/{{ site.cliVersion }}/evaluator.jar">CLI</a>, i.e., the command line interface, is a only the pure evaluator component to be executed manually.

Both software come as stand-alone `jar`s and you can run them via `java -jar evaluatorGui.jar` (in case of the GUI) and `java -jar evaluator.jar` in case of the evaluator.