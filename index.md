---
layout: lesson
title: Fitting models with `scipy.optimize`
---

Fitting models and testing the match of the models to the measured data is a
fundamental activity in many fields of science. In this lesson, we will learn
how to use non-linear optimization routines in `scipy.optimize`, to fit models
to data.

> ## Prerequisites {.prereq}
>
> Learners need to know how to use Python and Numpy, to the level taught
> in the Software Carpentry novice lesson.
>

> ## Getting ready {.getready}
>
> 1. Learners need to have the `scipy` library installed on their computers.
> If you have used your computer in a Software Carpentry workshop, it is likely
> that you already have it installed.
> You can test that by running the following in an IPython session:
>
> ~~~ {.python}
> import scipy
> ~~~
>
> If this raises an error, you might need to run the following in the unix
> shell:
>
> ~~~ {.input}
> $ pip install scipy
> ~~~
>
> Explanation: [pip](https://pip.pypa.io/en/stable/) is a python ['package manager'](https://en.wikipedia.org/wiki/Package_manager), which will go grab
> the necessary software for this lesson and install it on your machine.
> Another option is to use the [conda]() package manager in the unix shell as
> follows:
>
> ~~~ {.input}
> $ conda install scipy
> ~~~
>
> 2. You need to download some files to follow this lesson:
>
> - Make a new folder in your Desktop called `scipy-optimize`.
>
> - Download [scipy-optimize-data.zip](./scipy-optimize-data.zip) and move the file to this folder.
>
> - If it's not unzipped yet, double-click on it to unzip it. You should end up with a new folder called `scipy-optimize-data`.
>
> - You can access this folder from the Unix shell with:
>
> ~~~ {.input}
> $ cd && cd Desktop/scipy-optimize/scipy-optimize-data
> ~~~


## Topics

1.  [Introduction: models and why we like them](01-intro.html)
2.  [Linear models](02-linear-models.html)
3.  [Nonlinear models and optimization](03-nonlinear-models.html)
4.  [Model evaluation with cross-validation](04-cross-validation.html)
5.  [Summary](05-summary.html)

## Other Resources

*   [Reference](reference.html)
*   [Discussion](discussion.html)
*   [Instructor's Guide](instructors.html)
