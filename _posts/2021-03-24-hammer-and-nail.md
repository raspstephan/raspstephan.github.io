---
title:  "“If you have a hammer…” - 5 question to ask before starting a machine learning project"
comments: true
date:   2021-03-24 00:00:00 -0000
layout: single
classes: wide
author_profile: true
header:
  teaser: /assets/images/hammer-and-nail.jpeg
---

There is a saying that ["if you have a hammer everything looks like a nail"](https://en.wikipedia.org/wiki/Law_of_the_instrument). The lesson, of course, being that, even though hammers are an amazing tool for hammering nails, not every problem is a nail. I think we are currently experiencing such a hammer-and-nail situation when it comes to the application of machine learning or AI in science. AI, in particular deep learning, has done amazing things in areas like computer vision, natural language processing and game playing. So it’s only logical to ask as a scientist whether AI can also help us with the problems we are working on. However, amidst the hype, it is important to remember that not every problem is suitable for a machine learning approach. (Note: My expertise is in weather and climate research, so I will focus on this area, but many of the points I am making should also be applicable to other areas of science.)

![animation]({{ site.url }}/assets/images/hammer-and-nail.jpeg)

Despite an ever increasing number of AI publications, the number of studies that actually improve upon state-of-the-art techniques in weather and climate modeling remains low while most papers present a proof of concept. This is not a problem per se but it is important to remember that deep neural networks can pretty much do anything given enough data. This means that the question of whether AI can solve a problem better than an existing technique is often a practical one of whether enough data is available in the real problem setup. If the proof-of-concept setup is too far away from the real world problem, it often becomes hard to draw any conclusions from these studies. 

In most cases, it is not clear from the outset whether a problem is suitable for an AI approach, in which case the only way to find out is to try. However, it is important to think deeply about how to set up an AI project before embarking on the (often long and frustrating) journey (or having a PhD student embark on that journey). Having made many mistakes myself and having seen many examples of AI projects, some good, some bad, here are 5 questions (plus 2 bonus questions) to ask before starting an AI project in science.

1. What exactly is the problem I am trying to solve?
1. How exactly will I get my training data?
1. How exactly will I verify my results?
1. Am I still solving a real problem?
1. Is the project feasible within my constraints?

Bonus questions:
- (Hybrid modeling) Am I testing the skill that matters?
- (Explainable/interpretable AI) How will I use the output?


### 1. What exactly is my problem setup?
This question sounds trivial but the emphasis is on “exactly”. The problem setup is often just as or more important than the machine learning itself. Therefore, the first task is to write down in as much detail as possible what the inputs and outputs to the ML algorithm will be. This often greatly helps to clarify what the actual problem is and where there are still open questions. It is also really useful to do a thorough literature search at this stage and find the studies that are most similar to the problem at hand. If there are already a number of studies in a similar direction, it makes sense to ask how my study is different and whether it would make more sense to build upon an existing study/dataset. Defining the problem setup in detail from the start is also crucial for the next question.

### 2. How exactly will I get my training data?
Preparing the data will, in many cases, consume a shockingly large amount of time. For this reason it is incredibly important to think about this step carefully before actually touching the data. Here are some sub-questions to ask:

- Where will I get my data from? Do I need to create it myself and what will that involve? If the data is already available somewhere, how exactly will I get it? Do I need to obtain permissions? If I need to create the data myself (often the case in ML parameterization studies), which outputs do I need to save?
- How long will it take to download/create all the data? This can often take a surprisingly long time. For some weather archives (e.g. ERA5 on Copernicus), waiting in the download queue takes most of the time. Can I try downloading some test data to get an estimate? If the data download will take weeks or months, it’s best to start that as early as possible.
- Which preprocessing steps do I need to do (e.g. regridding or combining datasets)? Are there tools available to do this or do I need to write them myself? 
- How much disk space will I need and where will the processed data be stored?
- Lastly, and very importantly, how many samples will I have for training? Will I have enough samples to train anything much more complex than a linear regression? It’s hard to put a number on how many samples are enough but a thousand or more seems to be the absolute minimum to start thinking about deep learning. Of course, this depends on how correlated the data is and how difficult the task is. The actual number might be much higher. 

### 3. How exactly will I verify my results?
Baselines are key to meaningful AI studies. Without good baselines to compare the AI results to, it often becomes very hard to judge the quality of the trained algorithm. In many cases, AI methods are trained to replace traditional algorithms. If this is the case the state-of-the-art algorithm has to be included as a benchmark. Further, the evaluation metrics should reflect what is standard in the research area. It is also important, if possible, to include a simple ML algorithm like a linear regression or a random forest as comparison. It could turn out that the problem to be solved is actually quite simple and doesn’t require a complex neural network.

Many AI studies aim at speeding up simulations. For this they are often trained on expensive, high-resolution simulations. In this problem setup it is imperative to also include a state-of-the-art lower-resolution simulation as a baseline. 

Finally, it is important to think about the training/validation(/testing) split. How can I make sure that my validation is statistically significant (enough data) and fair (no accidental cheating). Setting aside data for validation and testing will of course also decrease the amount of data for training.


### 4. Am I still solving a real problem?
After going through questions 1-3, the original problem will almost certainly have changed a little. In many cases, simplifications will have to be made because of practical reasons like data volume or access. This is fine but it is important to ask whether, after turning the problem into a potential nail, the setup is still close enough to the “real” problem to be meaningful. Is there a clear path towards the real problem or is the real problem fundamentally different?

One common simplification is using a toy model. A classic case for this is ML parameterization research. Full complexity weather and climate models are very complicated, so it doesn’t really make sense to deal with them when we are not yet sure whether the approach will work at all. So it is useful to simplify the problem, by e.g. using an aquaplanet (no continents), reducing the number of physical parameters (no cloud water or ice) and running at lower resolution. If an approach works really well on this simplified problem, then there is a clear path how to go towards real climate modeling by adding one aspect at a time. However, there are also cases where the toy model can be too simple. It is common, for example, to use the Lorenz `96 dynamical system model for parameterization research. While this might be an interesting exercise for testing algorithms initially, this toy model is so far removed from the real problem that it’s very hard to draw any conclusions for real climate modeling. The path towards the real problem is, in this case, not clear. I’ve written about this topic in more detail [here](https://raspstephan.github.io/blog/lorenz-96-is-too-easy/). 

Another common case is using lower-resolution or synthetic data. Again, this makes sense since using full-resolution, full-complexity data is often computationally prohibitive and painfully time-consuming. However, as mentioned above, the crucial question in applying ML is often not whether ML is theoretically capable of solving a particular problem (in most cases, it is) but rather whether in the real world, enough training data is available. This does not mean that one cannot use “easier” data but the setting should reflect that of the eventual target application. It might be nice to have an algorithm that does really well on millions of synthetic samples when only hundreds are available for real data. Similarly, higher resolutions might require more complex networks and therefore more samples.

The important concept to keep in mind is that there should be a clear path from the chosen problem setup to the real problem. If I manage to build a good algorithm on my setup, what will be the next steps towards full complexity? If the path is not clear, it might be time to go back to questions 1-3.


### 5. Is the project feasible within my constraints?
Finally, it is important to realize that ML projects often require a significant amount of software and data engineering. From a science perspective, these aspects are rather unsexy and will be covered in one or two paragraphs in most papers. However, they might well constitute the vast majority of time and frustration. In academia, many AI projects will be executed by a single PhD or postdoc, many of which will have little experience in software engineering and handling large data volumes. This can often lead to frustrating experiences when a PhD student spends the first one or two years of their program battling data issues. This makes asking the first three questions above all the more important before sending a student on a potentially demoralizing journey. From a PI’s perspective, applying technique X to problem Y might sound like a straightforward project but the devil might be hidden in the details of data processing and scale. If a significant chunk of software and data engineering is required, it is important to make sure to have enough experience and support in the group to tackle such a task. 

Usually, setting up a machine learning project requires a balance between simplifying the problem enough to make it technically feasible within the constraints but at the same time not simplifying it too much to lose relevance to the real problem. In some cases, this might simply not be possible in traditional academia. This is where larger projects come in, such as the [Vulcan climate modeling group](https://www.vulcan.com/Special-Pages/Climate-Modeling.aspx), the [Climate Modeling Alliance](https://clima.caltech.edu/) or industry labs at Google, etc, where there are enough resources specifically for the engineering aspects of a project. 


## Bonus questions
The five questions above should apply to most AI applications in science. Below are two more questions that concern particular application areas, the first being hybrid ML-physics models, the second being interpretable and explainable AI.

### (Hybrid modeling) Am I testing the skill that matters?
A promising research area is using ML to improve and/or speed up physical simulations. Usually, this involves replacing a computationally expensive part of the simulation with a fast ML emulator or learning a correction term for a lower resolution simulation. In many cases, the first steps for these studies is to build a training data set using some reference simulation and then training a machine learning algorithm. Usually, the next step is evaluating the ML model on a hold-out validation dataset. However, for hybrid ML-physics models this “offline” evaluation is not enough. The crucial final step is to plug the trained model back into the simulation and run in “online”. Ample evidence shows that offline skill is not a reliable indicator for online skill, so that this last step is crucial for a meaningful study. Unfortunately, this step is often very challenging and time consuming, especially when the target simulation is a weather or climate model written in Fortran - yet another aspect to take into account when estimating how much work is associated with a project. I have also written a separate [blog post](https://raspstephan.github.io/blog/optimization-dichotomy/) about this issue.

### (Explainable/Interpretable AI) How will I use the output?
Explainable or interpretable AI (this also applies to parts of unsupervised learning) aims to use ML algorithms to learn something new about the emulated processes and perform a sanity check on the ML “thinking”. A classic example are saliency maps that show which areas a neural network focuses on when making a prediction. I am by no means an expert in this area but there are two issues I am often wondering about.

First, often we use our physical understanding to interpret the output of these explainable AI methods. If this is the case, do we really learn anything new? Can the method I am using give me enough evidence to form new hypotheses?

Second, it seems to me that it’s often not so clear what the next step from a newly discovered pattern is. How will I use this in my ongoing research? I think here it might help to play out a scenario of a hypothetical new pattern and think about how this would help in ongoing research. Otherwise, we might just be fishing for random patterns without knowing what to do with them.


## Final words
The questions I’ve formulated above are based on what I have seen in my own studies and from observing other projects over the last few years. There is a lot of exciting progress in AI for science but also a lot of “filler” publications that do not really advance the field. Naturally, not every study can be a major breakthrough but if designed well a project can be enlightening even if the outcome is that the problem is not a nail for our AI hammer. Especially with the rapidly increasing amount of funding going into AI research, I would encourage PIs to be very thoughtful in designing AI projects for their PhD students to avoid setting them up for a frustrating journey. 

I am very much looking forward to hearing other people’s perspectives.

#### Acknowledgements
I first heard about the hammer-and-nail analogy applied to this topic from Robert Pincus at the 2019 Oxford workshop that recently spawned this [special issue](https://royalsocietypublishing.org/toc/rsta/2021/379/2194). Thanks to Dave Clark for proofreading.
