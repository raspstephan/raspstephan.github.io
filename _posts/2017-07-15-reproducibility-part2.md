---
title:  "Reproducibility, Part 2 - My experiences"
comments: true
date:   2017-07-15 09:00:00 -0000
layout: single
author_profile: true
---

In my previous [blog post](https://raspstephan.github.io/2017/07/09/reproducibility-part1.html) I explained what reproducibility is, why it is important and how it could work in a practical sense. In this post, I will outline my personal efforts to implement reproducibility. At the end, I will ramble a little bit about my experiences and thoughts. But let’s start out with the technical issues.

**Model runs: The problem with non-open-source code and data**

The first issue I encountered was how to make my model simulations reproducible. The German Weather Service (DWD) does not make their model or data publically available. Whether this is reasonable or not is topic for another discussion. Here I will explain how I dealt with this situation, which I am sure applies to many others as well. The corresponding site on my github repository is [here](https://github.com/raspstephan/convective_variability_analysis/tree/master/cosmo_runscripts). There are two levels to my approach:
- Internal: One important point of reproducibility is to make sure others in your research group (or yourself) can easily find the necessary information and data to run similar experiments. For this purpose, I listed the paths to the directories where the data and the actual model binary files are stored. 
- External: For all external users, I tried to describe in as much detail as possible:  how I obtained my initial and boundary data; the model version which I used; and how the output is structured.

The model runscripts for all experiments are stored in the repository. This should make is easy to rerun the experiments. Additionally, the format of the model output is described.

**Data analysis: The power of a log-file**

My data analysis scripts are saved [here](https://github.com/raspstephan/convective_variability_analysis/tree/master/python_scripts). There are several Python scripts, most of which follow a two-step procedure. In the first step, the raw data are processed in some way. Each of the scripts corresponds to a certain type of processing. The preprocessed data are then saved in a NetCDF file since this step can take quite a long time. Then in the second step plots are produced from the preprocessed data. The python scripts take command line arguments which specify details about the analysis and plotting. 

The key element which makes these plots reproducible is a log string.  It is automatically created once the python script is called and then saved to the pre-processed NetCDF file. When producing a plot, this log string is loaded from the NetCDF file, another one is created and both the preprocessing log and the plotting log string are then saved as a text file with the same name as the figure. Examples for these log files can be found in this [Figshare repository](https://figshare.com/collections/convective_variability_poster_delft_jul_2017/3806629). Below are just the first few lines of one of these files: 

    Plotting log
    
    #####################################################
    Time: 2017-06-20T12:09:51

	Executed command

	----------------

	python variability.py --date_start 2016052800 --date_end 2016060800 --nens 50 --pp_name all_days_m_50_mems_inc_1h --plot_name all_days_m_50_mems_inc_1h --time_start 6 --time_end 24 --sep --var m --plot_type std_vs_mean --std_vs_mean_plot_inlay --plot_format png



	in directory: /home/s/S.Rasp/repositories/convective_variability_analysis/python_scripts



	Git hash: 67eb7714d0c91816399b85c3f67efaf386829123



	Full argparse parameters

	------------------------

	--plot_type std_vs_mean
	--sep True
	--date_end 2016060800
	--diurnal_title False
	...

As you can see, the log file contains information about the computing environment, the version of the code repository, as well as the arguments with which the script was called. This means to reproduce the figure, you simply have to check out the code repository at the given version and call the python script with the command given in the log file. 


**The publication: Tying it all together**

The last step to implement reproducibility is then to reference all this information in a publication. [Damien Irving](http://journals.ametsoc.org/doi/10.1175/BAMS-D-15-00010.1) suggests including a computation section. In a draft for an upcoming paper on my research I have written this:

*This subsection closely follows the guidelines on publishing computational results proposed by Irving (2016). The analysis and plotting of model and observation data was done using Python. In particular, for numerical computation the Python libraries NumPy (Numerical Python) and SciPy were used heavily. The raw plotting of the results was done using Matplotlib. The raw plots were then brought into their final form using the vector graphics program Inkscape.*
				
*To implement reproducibility of the results, each figure is accompanied by a log file published online in a Figshare repository. This log file contains information about the command which was executed to produce the figure, the version of the code repository and details on the installations of the software packages at the time the figure was produced. All code is accessible at https://github.com/raspstephan/convective variability analysis. A snapshot of the repository at the time of publication is also available on the Figshare repository. The README on the GitHub page gives more details on how to read the log files and how to use the Python analysis scripts. Since DWD does not provide their models and data as open source, the model code and data used and produced is only saved internally. A detailed description of how the simulations were produced, including the model namelists, is, however, provided in the cosmo runscripts directory of the GitHub repository.*

**My experiences and thoughts**

First of all, let me point out that what I described here is by no means how I think everyone should do it. It's simply one solution I came up with for my particular situation. There definitely are plenty of things which could (and probably) should be improved. So here are just some thoughts which occurred to me during this process. 

Implementing reproducibility after the fact is a lot of work. I had already written code for most of my analysis. I spent around two to three weeks completely rewriting my code. On the upside, this forced me to really think about the assumptions and details of my analysis. I still would not recommend doing it for an already existing project, however. For a new project though I believe that clean coding can save time in the end.

The biggest hindrance I encountered was my lack of knowledge how to structure code well. I think that this is a general issue in science these days. Many scientists spend a large portion of their time programming, but few have learn how to do so beyond some introductory courses. 

Finally, I do wonder whether some aspects are overkill. There is no doubt for me that good coding has plenty of benefits, but I am undecided about the additional effort of producing log files and making everything publicly presentable. 

At this point, I do not want to cast a final verdict. For now, I will continue writing code in a similar fashion. Time will tell how beneficial it turns out to be. 

I would love to hear everyone's thoughts and suggestions.

