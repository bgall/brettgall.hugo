---
title: Simulation-based Power Calculations for Conjoint Experiments
author: Brett J. Gall
date: '2019-12-03'
slug: conjoint-power-simulations
categories:
  - Programming
  - Statistics
  - Teaching
tags:
  - Programming
  - R
  - Conjoint Experiments
  - Power Calculations
  - Simulation
  - Teaching
---

Social scientists rarely provide explicit justification for choices that directly affect the suitability of their research designs for providing evidence for or against their hypotheses. While recent developments - such as the development of pre-registration plans - encourage researchers to think more carefully about the ability of their studies to precisely identify the sign and magnitude of the relationships between theoretical constructs, it still remains that case that few researchers justify the statistical power of their designs. While almost no observational studies conduct *a priori* power calculations, even [carefully developed pre-registration plans](https://dataverse.harvard.edu/file.xhtml?persistentId=doi:10.7910/DVN/WX5UXL/1ACTAA&version=2.0) often omit power analyses.

One explanation for the lack of power analyses is that researchers fear the truth: oftentimes, the available data or the data the researcher can afford to collect is insufficient. Many prospective designs are simply doomed to either fail to detect an effect or dramatically overestimate the magnitude of the effect. After all, the sample sizes required to detect even moderately-sized effects with high probability in relatively simple designs [often dramatically exceed the size of the typical study](https://twitter.com/aecoppock/status/983443245328891905?lang=en).

Alternatively, researchers may lack the knowledge or tools to conduct power analyses. For example, while recently designing a conjoint experiment, I discovered that many of the readily-available tools for conducting power analyses are poorly suited for conjoint experiments - particularly when researchers are interested in complex estimands and designs. This can perhaps explain the conspicuous absence of power calculations for conjoint experiments. Without canned power calculators or guides, many well-intentioned researchers won't know what to do or how to do it. Introducing tools that lower the barriers to researchers performing power analyses hopefully will increase the prevalence of these analyses. In turn, this will hopefully lead to more efficient, ethical use of resources on empirical projects that are not-so-ill-fated.

To this end, I developed some code to analyze the effects of design and modeling choices - such as estimand choice or choices over the number of participants, attributes and tasks  - on the statistical power of conjoint designs via simulation in R and packaged some of it in tutorial to help others develop their own code. By laying out the logic behind each step of the code and providing some canned functions (and discussion of how to modify the code to your own analyses), hopefully you will have some building blocks for your own analyses.

You can find the tutorial as an Open Science Framework Preprint: [Simulation-based power calculations for conjoint experiments](https://osf.io/bv6ug)
