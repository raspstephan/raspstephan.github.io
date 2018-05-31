---
layout: page
title: Weather Research
permalink: /weather_research/
---

This page highlights my research in numerical weather prediction and atmospheric dynamics.

**Research projects**

- [Stochastic boundary layer perturbations in convective-scale ensemble forecasting](#stochastic)
- [Convective variability and clustering](#variability)  
- [Convection-permitting simulations of Warm Conveyor Belts](#wcb)

*I have also made a commitment to reproducible research, which you can read about [here](https://raspstephan.github.io/2017/07/09/reproducibility-part1.html).*

---

### Stochastic boundary layer perturbations in convective-scale ensemble forecasting <a name="stochastic"></a>

In collaboration with the German Weather Service (DWD) we are testing the impact of phsically-based stochastic boundary layer perturbations ([PSP](http://dx.doi.org/10.1175/JAS-D-15-0144.1)) in a km-scale ensemble data assimilation and forecasting system, COSMO-KENDA. 

Preliminary results suggest that the PSP scheme improves the representation of convection in weak synoptic forcing situations but might be slightly detrimental in strong synoptic forcing. Furthermore, the ensemble spread seems increased, particularly in the first guess ensemble.


### Variability and clustering of mid-latitude summertime convection <a name="variability"></a>

See publication [here](https://journals.ametsoc.org/doi/10.1175/JAS-D-17-0258.1).

In this project, we were investigating the variability and clustering of continental summertime convection. Understanding the way convection behaves is important to improve the representation of clouds in global weather and climate models. Most models are too coarse to resolve convection explicitely and therefore have to rely on parameterizations. Typically, this is done in a deterministic fashion, meaning that similar large scale atmospheric states result in similar convective responses. In reality, however, clouds behave chaotically. 

Stochastic parameterizations are one way of including this uncertainty about the sub-grid response in an atmopheric model. To design such a stochastic parameterization, however, one requires a theory about the convective variability. Such a theory was proposed by [Craig and Cohen (2006; CC06)](http://dx.doi.org/10.1175/JAS3709.1). In this work, we aimed to test this theory, outside of its comfort zone: in the continental mid-latitudes. Here, convection is influenced by a number of factors not included in the CC06 theory: diurnal variations in solar radiation, orography, land surface heterogeneities, and many others. 

We quantified convective variability in 12 days on high-impact convection over Germany using the stochastic boundary layer perturbations mentioned above. We found that the theory still works well over a wide range of scales. In particular the mass flux standard deviation scales with the square root of the mean mass flux, in agreement with the CC06 theory. In contrast, multiplicative perturbation schemes such as SPPT assume a linear scaling which does not fit with our data.

There are however deviations from the CC06 theory. Most prominently, cloud organization influences the variability of convection. Clouds tend to be more clustered in the morning and evening on scales or around 100 km, which causes larger variability. Our findings suggest that the inclusion of convective organization could also lead to improvements for stochastic schemes.

Furthermore, we found that the individual clouds follow an exponential mass flux distribution but only if the identified cloud objects are separated into individual updraft cores. The congregated cloud objects follow a power-law distribution which agrees with a recent study by [Windmiller](https://www.mpimet.mpg.de/en/staff/julia-windmiller/) and Craig. 

In general, our study supports the applicability of the CC06 theory in stochastic parameterizations such as the [Plant and Craig (2008)](http://dx.doi.org/10.1175/2007JAS2263.1) scheme in global simulations but also highlights areas which could benefit most from further research. Particularly, the parameterization of convective organization seems to be an important issue, which has flummoxed many scientists so far.



### Convection-permitting simulations of Warm Conveyor Belts <a name="wcb"></a>

In my master's thesis and the subsequent [publication](http://dx.doi.org/10.1175/MWR-D-16-0112.1) we investigated, for the first time, air parcel trajectories in extratropical cyclones using convection-permitting simulations. Our main focus was to investigate the importance of convection in the ascending air streams. 

![animation]({{ site.url }}/assets/result.gif)  
*The animations above show the simulations of the three cases which were chosen for this study. JAN is the winter case, JUL the summer case and OCT the autumn case. The elongated lines of precipitation (blue shading) coincide with the locations of the cold front, along which the tracked air parcels (dots, colored by their pressure) ascend. Also shown is the convective available potential energy (CAPE), a measure of how unstable the atmosphere is, in the red shading. The thin black lines show the geopotential height contours.*

Check out the popular science article ([English](http://www.en.meteo.physik.uni-muenchen.de/aktuelles/forschungshighlights_archiv/rasp_etal_2016_trajectories/index.html) and [German](http://www.meteo.physik.uni-muenchen.de/aktuelles/forschungshighlights_archiv/rasp_etal_2016_trajectories/index.html)) that I wrote for our institute's home page. 

