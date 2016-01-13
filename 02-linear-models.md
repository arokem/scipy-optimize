---
layout: page
title: Linear Models
minutes: 10
---

# Linear models

> ## Learning Objectives {.objectives}
>
> * Learners can identify a linear model.
> * Learners can use `np.polyfit` to fit a linear model to data


The main distinction we will make in this lesson is between linear models and
non-linear models. Linear models are models that can be described by the
following functional form:

    $\bf{y} = \beta_0 + \beta_1 \bf{x}_1 + \beta_2 \bf{x}_2 + ... + \beta_n \bf{x}_n + \epsilon$,

where $\bf{y}$ denotes the dependent variable or variables (that's why it's
bold-faced: it could be a vector!) in your experiment. $\bf{x}_i$ are sets of
dependent variables (also, possibly vectors) and $\beta_i$ are parameters.
Finally, $\epsilon$ is the noise in the experiment. You can also think about
$\epsilon$ as all the things that your model doesn't know about. For example, in
the visual experiment described, changes in participants wakefulness might
affect performance in a systematic way, but unless we explicitely measure
wakefulness and add it as an independent variable to our analysis (as another
$\bf{x}$), we don't know it's value on each trial and it goes into the noise.

Linear models are easy to fit. Under some fairly generic assumptions (for
example that $\epsilon$ has a zero-mean normal distribution), there is actually
an analytic solution to this problem. That is, you can plug it into a formula
and get the exact solution: the set of $\beta$ that give you the smallest
sum-of-squared-errors (SSE) between the data you collected and the function
defined by the parameters (we will assume that this is your objective, though
variataions on this do exist). This is the reason that if you can transform your
data somehow to get it into a linear form, you should definitely do that.

Let's fit a linear model to our data. In our case, a linear model would simply
be a straight line:

    $y = \beta_0 + \beta_1 x$

These kind of equations (*polynomials*) can be solved using `np.polyfit`:
