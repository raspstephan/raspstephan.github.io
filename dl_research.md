---
layout: page
title: Deep Learning Research
permalink: /dl_research/
---

This page highlights my research in applying machine learning to problems in atmospheric science. Since the projects are all work-in-progress, this website just offers teasers. More to come soon!

**Research projects**

- [Representing climate model physics](#cbrain)
- [Post-processing of probabilistic numerical weather forecasts](#variability)  

*I have also made a commitment to reproducible research, which you can read about [here](https://raspstephan.github.io/2017/07/09/reproducibility-part1.html).*

---

### Representing climate model physics <a name="cbrain"></a>

The representation of clouds in climate models is the major cause for uncertainty in climate predictions. The highly chaotic nature of turbulence and microphysics inside a cloud has vexed atmospheric scienctist for decades. In this work we want to provide a proof-of-concept that neural network can offer a way out. 


### Post-processing of probabilistic numerical weather forecasts <a name="ppnn"></a>

Numerical weather forecasts have systematic biases which need to be corrected before giving them to an end user. Traditionally this is done with simple linear models. We explored the feasibility of using neural network to capture more complex behavior. We achieved state-of-the art results at a fraction of the computational cost of the traditional techniques.