---
title:  "Deep Learning (for Atmospheric Scientists): How to get started"
comments: true
date:   2019-02-05 00:00:00 -0000
layout: single
classes: wide
author_profile: true
---

*Updated version of an earlier post after version 3 of fast.ai has been released.*

**tl;dr**: There are currently two great resources for getting started with deep learning: [fast.ai](https://course.fast.ai/) and [deeplearning.io](https://www.coursera.org/specializations/deep-learning). fast.ai is great for people who love to learn by doing. deeplearning.ai follows a more traditional style of teaching. Both are great. I recommend trying the first lectures of both to see which one suits your style better. Plus other helpful resources and books.

## Machine learning and deep learning are not hard!
Over the course of the last year, I have given several presentation on my deep learning research. One common question I got after these talks has been: What are good resources if I want to get into deep learning? In this post I want to summarize the best resources I know of. But first, I want to start by dispelling one common misconception, which is that deep learning is really hard. It is not!

Of course, many deep learning companies and researchers have a vested interested in portraying their work as super-complex. But the truth is that with some basic knowledge of linear algebra (and I really mean basic) and a bit of experience in coding, you will be able to apply deep learning to actual problems in no time. Of course, techniques at the cutting edge of deep learning research (e.g. [CycleGAN](https://github.com/junyanz/pytorch-CycleGAN-and-pix2pix)) require a bit more familiarity with the deep learning literature and background; but the truth is that for most applications to problems in other fields of science standard neural networks with some minor tweaks are quite sufficient. For my deep learning papers, for example, the actual neural network part of the code was just a few lines long. So if you are interested in the topic just give it a go!

## Online courses: fast.ai and deeplearning.ai

The best way to get started with deep learning is with an online course. Currently, there are two stand-out courses: [fast.ai](https://course.fast.ai/) and [deeplearning.io](https://www.coursera.org/specializations/deep-learning). Both are a great place to start but they do follow a different style of teaching. 

### fast.ai

fast.ai is how I got started about a year and a half ago and it completely transformed my working life. fast.ai has been created by Jeremy Howard and Rachel Thomas with the goal to make deep learning easy and accessible for a broad audience. Their free online course consists of two hour lecture videos and the corresponding Jupyter notebooks. The focus is really on learning by doing. In the first lesson, you will start by training a state-of-the-art image classification network in the first lecture without really knowing what's going on. Only in later lessons, once you have already developed some intuition will you delve deeper into the details of the algorithm.

This sort of top-down approach might be intimidating at first because it is contrary to how we have been conditioned to learn in school and university. But it helps you to develop an intuitive understanding that is particularly important in machine learning. I, too, was skeptical when I started fast.ai but after just a few weeks I realized that I have probably never learned as much in such a short amount of time. 

fast.ai's main course is "Practical Deep Learning for Coders", the third version of which has just been released. In this course, the focus is on using state-of-the-art deep neural networks for image recognition and natural language processing. 

fasti.ai uses their own neural network Python library, called fastai (no dot...) which is built upon Pytorch. This library automatically implements many best practices for common deep learning tasks. One downside of this is that many applications we Earth scientists might be interested in are not common deep learning tasks and do not use common deep learning data formats. Here, using fastai is slightly more complicated. However, in the course you will also learn how to use plain Pytorch which allows you to do pretty much anything you want.

fast.ai also offers a course [Introduction to Machine Learning for Coders](http://course18.fast.ai/ml) which covers machine learning from a more fundamental point of view. The first half of this course covers random forests, while the second half is focused on neural networks. This is also a great place to learn good machine learning practices. 

So which course should you do? I will discuss this further below.

### deeplearning.ai

deeplearning.ai offers a five course specialization on Coursera. The lessons are tought by machine learning legend Andrew Ng. These courses follow a more traditional teaching philosophy, starting at the basics and increasingly covering more complex topics. I personally have not done these courses, but have heard good things about them. The topics are covered in several short videos along with programming assignments based on Keras. 

The courses are free to audit (watch the videos and work on the assignments) but in order to get a certificate and scoring for the assignments you need to pay $42 per month. There is a 7 day free trial, however, and always remember to ask your university for funding options.

## Other resources

### The Matrix Calculus You Need For Deep Learning

If you feel like refreshing (or learning for the first time) the matrix calculus that sits at the core of deep learning, this is a great concise [paper](https://arxiv.org/abs/1802.01528) by Terence Parr and Jeremy Howard who we know from fast.ai.

### Michael Nielsen's online book

If you prefer reading over watching videos and if you are more inclined towards the mathematics of deep learning, Michael Nielsen wrote a fantastic online book called [Neural Networks and Deep Learning](http://neuralnetworksanddeeplearning.com/) that also comes with code.

### Francois Chollet's Keras book

Francois Chollet is the developer behind Keras. He recently authored a book called [Deep Learning in Python](https://www.manning.com/books/deep-learning-with-python) which gives a practical introduction to machine learning practices and solving common tasks using the Keras API. 

### The internet: documentations, blog posts, and so on...

The great thing about machine learning is that so many people are doing it and they are very active online. So if you have any question, just type it into Google and most likely you will find an answer on Stackoverflow or some blog. Another great resource are the documentation pages of common DL frameworks, like Keras and Pytorch. Often these will give you concise tutorials that are a great place to get started with a new language. 

## So many options: what to do?

My recommendation is to check out the first lessons of the fast.ai deep learning course and deeplearning.ai and just see which one you like better. Don't worry about the fact that they are using different Python libraries. Once you have a better understanding of the concepts of deep learning, it is easy to switch between different libraries.

The most important thing is to get started. You will soon discover that deep learning is not magic and that you will soon be able to use neural networks for your problems. 

