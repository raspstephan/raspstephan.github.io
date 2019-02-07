---
title:  "Deep Learning (for Atmospheric Scientists): How to get started"
comments: true
date:   2018-01-14 00:00:00 -0000
layout: single
author_profile: true
---

In the last few weeks I gave several presentations on applying neural networks to problems in weather and climate science. Many people expressed an interest  in this topic and asked me to recommend resources to learn more about deep learning. For this reason I thought I would share with you my experiences getting into deep learning. 

## Two approaches to learning: Bottom-up vs top-down
There are two basic approaches to learning a new topic. In the bottom-up approach you start by learning the basics and then progressively advance to more complex topics. This is by far the most common way of teaching in schools and universities. For deep learning this would mean starting with the mathematical basics, then progressing concept-by-concept until at the end you’ll be able to build a cutting-edge neural net.

The top-down approach turns these principles upside down. Instead of starting from the very basics, you start by looking at the big picture and then peel back the layers. Here, you’ll start out by building that cutting-edge neural net (which thanks to modern libraries and great educators is pretty easy) without really knowing what’s going on behind the scenes. Then after developing some intuition, gradually you’ll delve deeper into the details of the algorithms. 

Mathematician [Paul Lockhart](https://www.maa.org/external_archive/devlin/LockhartsLament.pdf) uses the analogy of a child learning to play an instrument to illustrate the advantages of top-down learning: When a kid learns to play, say, the piano, it doesn’t start by mastering music notation and the physics of piano string vibrations before finally, a decade later, touching the instrument for the first time. Rather you show the child some basic chords and let them play, thereby developing intuition and feeling for the instrument. 

Having gone through a lifetime of bottom-up learning it might seem daunting to just apply a technique without really understanding what actually makes it work. I, too, was sceptical at first. But after just a few weeks of going through the fast.ai courses (see below) I realized that I have probably never learned as much in such a short amount of time. Having said that, people are different and for some people the bottom-up approach might be more suitable. Here I will talk about great resources for both styles of learning. 

## Deep learning with the top-down approach: Fast.ai
[fast.ai](http://www.fast.ai/) was created by [Jeremy Howard](https://twitter.com/jeremyphoward) and [Rachel Thomas](https://twitter.com/math_rachel) with exactly this top-down approach in mind. They offer free online courses based on two hour lecture videos to present an overview and then encourage student to code things up themselves to understand what’s really going on. Starting with only a broad concept of what a neural network is, students learne how to build cutting-edge image classification networks, train a recurrent neural network to write text character-by-character and much more in just a few weeks. To really delve deep requires a significant investment of time, however, because most of the learning happens by going through the code oneself. To get the most out of the courses I would recommend spending at least an hour a day on average, but there certainly is no harm in checking out one or two lecture videos to see if you like it. 

![animation]({{ site.url }}/assets/images/fastai_screenshot.jpeg) 
*Jeremy Howard (fast.ai) using a Jupyter notebook and Keras to create a state-of-the-art convolutional neural network in just a few lines of code.*

Currently (January 2018), the course offerings at fast.ai are a little confusing. On their main website they have [Practical Deep Learning for Coders, Part 1](http://course.fast.ai/) and [Cutting Edge Deep Learning for Coders, Part 2](http://course.fast.ai/part2.html). There is however an [newer version of Part 1](http://forums.fast.ai/t/unofficial-release-of-part-1-v2/9285?u=raspstephan) on their forums forums.fast.ai which has not officially been released. So far I have only watched the first two lecture videos of the new version. The big difference between the old and the new version is that version 1 is based on Keras, a wonderfully simple but still powerful neural network library, while version 2 is based on their own library sitting on top of Pytorch, a lower-level neural network library, which allows you to do almost anything. At this time, as someone trying to apply these techniques to my field, I would still recommend doing the older version. This is mainly because applying neural networks in atmospheric science or physics often requires slightly different methods than the traditional image or natural language processing tasks tackled in the courses. For this flexibility Keras might be an easier choice than their own fast.ai/Pytorch library. As I am going through version 2, however, I might change my opinion and will keep you updated.

## Bottom-up resources: deeplearning.ai and others
On [Coursera](https://www.coursera.org/), there is a new deep learning curriculum created by [Andrew Ng](https://twitter.com/AndrewYNg) called [deeplearning.ai](https://www.coursera.org/specializations/deep-learning) which is made up of 5 courses, starting right at the basics of neural networks. You can audit the course (watch all the videos and look at the assignments) but to actually get the solutions and a certificate at the end you have to pay a monthly fee of 41€ (there is a 7-day free trial and remember to ask your institution if they cover the costs). I have not taken the course myself, but I have taken a previous course on machine learning by Andrew Ng and it served as a good elementary introduction. 

![animation]({{ site.url }}/assets/images/nielsen_backprop.jpeg) 
*An explanation of the backpropagation algorithm at the heart of how neural networks learn from Michael Nielsen’s online book.*

If you prefer reading over watching videos [Neural Networks and Deep Learning](http://neuralnetworksanddeeplearning.com/) is a fantastic online book by Michael Nielsen, which also explains neural networks and delves a little deeper into the mathematics and concepts behind the algorithms. I have used this resource many times trying to understand what is really going on under the hood. 

There is a multitude of other resources out there. Coursera, edx, udacity and many others offer introductory courses. A Google search will turn up even more. The ones mentioned above are just the resources I am familiar with.

## Just try it out!
Deep learning and neural networks are a fascinating topic to learn about. Thanks to many easy-to-use Python libraries and great educational resources you will be able to do a lot in a short amount of time. If you are the competitive type you could participate in a Kaggle competition or you could apply what you have learned to your own research field. Since deep learning is such a new field, chances are that in most areas of research nobody has even though about how one could apply neural networks. And while there is a lot of hype about deep learning, I also think this is a pretty exciting position to be in. For everyone interested my strong suggestion is to simply try it out. Just start watching the fast.ai videos and see if they are for you but beware, you might get sucked into it like I did or you might discover that it is not for you which is also totally fine. 


