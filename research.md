---
layout: page
title: Research
permalink: /research/
---

**Current research projects**

- [Stochastic boundary layer perturbations in convective-scale ensemble forecasting](#stochastic)
- [Convective clustering and organization](#variability)  

**Previous research**

- [Convection-permitting simulations of Warm Conveyor Belts](#wcb)

---

## Current research projects

### Stochastic boundary layer perturbations in convective-scale ensemble forecasting <a name="stochastic"></a>

The aim of this project, which is run in cooperation with Deutscher Wetterdienst (DWD) is to test the impact of the physically-based stochastic boundary layer perturbation scheme (PSP) proposed by [Kober and Craig (2016)](http://dx.doi.org/10.1175/JAS-D-15-0144.1) in an operational data assimilation and ensemble forecasting system, COSMO-KENDA. In particular, we want to investigate the systematic effect of these perturbations on the diurnal cycle of convective precipitation, as well as on the ensemble spread. 

The PSP scheme aims to reintroduce variability in the boundary layer which has gone missing because the grid spacing (2.8 km in our case) is too coarse to resolve all turbulent motions. Since turbulence is a crucial factor for triggering convection, this lack of variability can lead to systematic biases in the timing and intensity of convection. 

Another common shortcoming of current convective-scale ensemble forecasting systems is a lack of ensemble spread. Models are often too certain of their predictions, resulting in unreliable forecasts. Stochastic perturbations have proven to be a powerful method to improve the spread-skill ratio in global models (e.g. SPPT at ECMWF). We now want to see whether the small scale perturbations we are introducing can have a similar beneficial impact. 

**Current status**  
We are currently in the process of analyzing the data assimilation analyses and free forecasts for a two week period of high impact weather over Germany.


### Convective clustering and organization in the mid-latitutes <a name="variability"></a>

In this project, we are investigating the clustering and variability of continental, summertime convection. To understand the way convection organizes is important in order to improve convection paramterization in global weather and climate models. Currently, most models which are too coarse to explicitly resolve deep convection make very simplistic assumptions about the sub-grid clouds. In nature, however, clouds tend to organize changing their life cycle. Additionally, two very similar large-scale atmospheric conditions can give rise to two very different looking cloud ensembles. All this means that classic, deterministic parameterizations are often a poor representation of what is actually going on in the atmosphere.

The first key result of our research is that for summertime convection, there is a stong diurnal variation in the clustering of clouds. As convection is strongest (from noon to early afternoon) convection is only weakly organized. In the evening hour, however, clouds become strongly clustered.

The second focus of our research was to test the theory of convective variability proposed by [Craig and Cohen (2006)](http://dx.doi.org/10.1175/JAS3709.1). This theory assumes a very simple model of atmospheric convection based on statistical physics. Its predictions agree well with convection-permitting simulations of radiative convective equilibrium. We find that the basic assumptions still hold well for our much more complex simulations, but adjustments need to be made for the changes in convective clustering. This result further supports ongoing development and use of the stochastic convection parameterization by [Plan and Craig (2008)](http://dx.doi.org/10.1175/2007JAS2263.1)

**Current status**
Weare currently fine-tuning our analysis and writing up the results for publication!

## Previous research

### Convection-permitting simulations of Warm Conveyor Belts <a name="wcb"></a>

In my master's thesis and the subsequent [publication](http://dx.doi.org/10.1175/MWR-D-16-0112.1) we investigated, for the first time, air parcel trajectories in extratropical cyclones using convection-permitting simulations. Our main focus was to investigate the importance of convection in the ascending air streams. 

![animation]({{ site.url }}/assets/result.gif)  
*The animations above show the simulations of the three cases which were chosen for this study. JAN is the winter case, JUL the summer case and OCT the autumn case. The elongated lines of precipitation (blue shading) coincide with the locations of the cold front, along which the tracked air parcels (dots, colored by their pressure) ascend. Also shown is the convective available potential energy (CAPE), a measure of how unstable the atmosphere is, in the red shading. The thin black lines show the geopotential height contours.*

Check out the article ([English](http://www.en.meteo.physik.uni-muenchen.de/aktuelles/forschungshighlights_archiv/rasp_etal_2016_trajectories/index.html) and [German](http://www.meteo.physik.uni-muenchen.de/aktuelles/forschungshighlights_archiv/rasp_etal_2016_trajectories/index.html)) that I wrote for our institute's home page. 

