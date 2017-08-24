---
layout: post
title:  "A simple hack to make figures reproducible"
comments: true
date:   2017-08-24 00:00:00 -0000
---

In my [previous posts](https://raspstephan.github.io/2017/07/09/reproducibility-part1.html) I explained why reproducibility is an important topic that is probably underappreciated in the weather and climate sciences at the moment. Here, I just wanted to present a simple hack which makes figures created with the Python library `matplotlib` more reproducible. 

The basic idea, based on Damien Irving’s [inspiring paper](http://journals.ametsoc.org/doi/abs/10.1175/BAMS-D-15-00010.1), is to save a log file along with each figure. The file has the same name as the figure file but with the ending `.log` instead of `.pdf` or whatever format the figure is in. The log file contains information about:
- When the script was called.
- Which script was called to produce the figure and which arguments were used (using the `sys.argv` command).
- The git commit at the time (using the package `GitPython`, which you might need to install additionally). For this to work changes should be committed regularly of course. 
- Which Anaconda environment was used.

<script src="https://gist.github.com/raspstephan/4b2f77e950d5da99466612fde133bd52.js"></script>

Here is an example of such a log file: 

	Time: 2017-08-17T11:55:15

	Executed command:

	python verif_fc_prec.py --expid DA_REF DA_PSPv2 DA_REF_TL500 DA_PSPv2_TL500 noDA_PSPv2 --ana det --date_start 20160526000000 --date_stop 20160609000000 --composite

	In directory: /home/s/S.Rasp/repositories/dwd_scripts

	Git hash: ba7f57f8a55b63af0c9eb53e9231e58da3d33e79

	Anaconda environment: py_env                *  /home/s/S.Rasp/anaconda2/envs/py_env


From this information it should be easy to reproduce the respective figure. The only change required is to replace the usual `savefig` call with a call to the function `save_fig_and_log`. A similar method could be used to trace intermediate steps, such as pre-processing data. 

Certainly there are more elegant solutions. But hopfully this code snippet can provide a good starting point for implementing reproducibility and serve as inspiration for better solutions. As always I am very interested to hear your opinions. 

