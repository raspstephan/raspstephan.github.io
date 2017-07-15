---
layout: post
title:  "Reproducibility, Part 1 - What is it and how to start?"
comments: true
date:   2017-07-09 09:00:00 -0000
---

*Before I start let me thank and give credit to [Sebastian Lerch](https://sites.google.com/site/sebastianlerch/) of the Heidelberg Institute for Theoretical Studies (HITS), whose slides on the topics served as an inspiration for this post, and [Georgios Fragkoulidis](http://www.w2w.meteo.physik.uni-muenchen.de/people/phd_students/fragkoulidis_georgios/index.html) of Johannes Gutenberg-University in Mainz for initiating our discussion on the topic at the Early Career Scientist meeting of our project [Waves to Weather](http://www.w2w.meteo.physik.uni-muenchen.de) this spring.*   

Science has a “reproducibility crisis”. Several high-publicity reports have emerged over the last few years, claiming that many results published in scientific journals cannot be reproduced. Take [this](http://www.bbc.com/news/science-environment-39054778) as an example or just google *reproducibility crisis* for a variety of recent articles. While the life sciences were hit hardest by this criticism, common practices in computational science - which includes most of weather and climate research - were also heavily scrutinized.    

**What is computational reproducibility anyway?**   

[Victoria Stodden](https://ischool.illinois.edu/people/faculty/vcs), one of the people at the forefront of the “reproducibility movement”, defines the first principle of scientific computing as follows: 

“Authors should include in their publications the data, algorithms, or other information that is central or integral to the publication—that is, whatever is necessary to support the major claims of the paper and would enable one skilled in the art to verify or replicate the claims.” ([Stodden and Miguez 2014](http://doi.org/10.5334/jors.ay))

Renowned Stanford statistician [David Donoho](https://statweb.stanford.edu/~donoho/) puts it even more drastically:

“The idea is: An article about computational science in a scientific publication is not the scholarship itself, it is merely advertising of the scholarship. The actual scholarship is the complete ... set of instructions [and data] which generated the figures.” (Donoho 1998)

I would argue that in our field of research the interpretation of the results is equally important, but that does not change one fact: Most publications in climate and weather science fail to include the data and the code used to analyze and plot the data. 

**The moral and practical arguments for reproducibility**

But why should we care about reproducibility? First, there is the moral point of view. The American Physical Society states the [this](https://www.aps.org/policy/statements/99_6.cfm) as one of its core principles: 

“The success and credibility of science are anchored in the willingness of scientists to (…) Expose their ideas and results to independent testing and replication by others. This requires the open exchange of data, procedures and materials.”

This means that the scientific method is at stake. Failure to disclose all information on scientific research can hurt the credibility of science. This was evident in several medicine related cases over the past few years. But climate science has had its own scandal, [Climategate](https://en.wikipedia.org/wiki/Climatic_Research_Unit_email_controversy), which shows that free sharing of data and methods is highly important. 

There are also practical reasons for implementing reproducibility.

Computational reproducibility requires well written and documented code which can reduce errors. Code can then also be shared more easily.

Clear documentation of how figures were produced also makes it easier for new researchers to pick up the research of departed colleagues. This is particularly relevant in multi-stage projects, such as our Waves to Weather project.

Finally, reproducible analysis is good advertisement: First, for the science itself. It shows that considerable care has been taken producing and analyzing the data, which lends credibility to the results. And second, personally as it shows commitment to careful work to potential future employers.

So all these points sound pretty good, but why do we see reproducibility so rarely in action?

**That sounds like a lot of work, and where would I even start?**

The most common response from people after hearing about reproducibility is: “That sounds like a lot of work! Don’t you think this is overkill for our kind of work?”

Then there are concerns about copyright. On the one hand, code or data from other sources might not be open-source. On the other hand, people might be worried that putting their piece of innovative code out there on the internet will allow other researchers to “steal” their results.

But even if all these mental hurdles are passed, and you are motivated to make your research reproducible, there is still the biggest issue of all: How?

Most of us spend a large portion of their time writing code, but very few have received any kind of software development training. So how would you even know where to start? I certainly had no idea.

**A practical guide for the regular scientists**

Luckily, some very useful resources have been published recently, which offer concrete guidelines and advice to write better, reproducible code.

First, I would like to highlight the two papers on *Scientific Computing* by Greg Wilson et al. ([Part 1](https://doi.org/10.1371/journal.pbio.1001745) and [Part 2](https://arxiv.org/abs/1609.00037)). They give practical tips on how to write better code, step by step. The papers are short and easy to read. I would definitely recommend checking them out!

I would like to focus on another recently published paper by [Damien Irving](https://drclimate.wordpress.com), titled: [*A Minimum Standard for Publishing Computational Results in the Weather and Climate Sciences*](https://doi.org/10.1175/BAMS-D-15-00010.1). I found the fact particularly appealing that he did this work on reproducibility during his PhD research in climate dynamics. 

His suggestions are aimed at the “regular” scientist, so you and me (most likely), who analyzes datasets and produces figures. Again, I would highly recommend reading this paper, it’s not very long. His key suggestions are to include in each paper: 

- A computation section: This includes details on the software and computing environment along with references to the code repository and data.
- A corresponding code repository (on [Github](https://github.com), for example): This contains all the code used to analyze and plot the data.
- A log-file for each figure: This lists the commands/programs which were used to produce the figure. 

A nice example of these recommendations in action can be found in Damien Irving’s publications.

**The self-experiment**

After discussing this topic at our Early Career Scientist Meeting earlier this year, I was motivated to implement reproducibility in my own research. I was still left with some hesitation and uncertainty whether it would be worth it, but I thought I’d give it a try. 

In a follow up [blog post](https://raspstephan.github.io/2017/07/15/reproducibility-part2.html) I discuss my personal experiences and certain issues I encountered. 
