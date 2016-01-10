---
layout: page
title: Introduction
minutes: 10
---
# Introduction: why model?

> ## Learning Objectives {.objectives}
>
> * Learners will define modeling.
> * Learners will debate the utility of modeling for their data.
> * Learners will identify different strategies for fitting models.

To understand why you would want to fit models in your research, let's first
consider an example from my own research: A data-set taken from an experiment in
visual neuroscience (this experiment was conducted in collaboration with my
colleague [Ayelet Landau](http://www.landaulab.com/ayelet-landau.html), while
she was at the Ernst Strungmann Institute in Frankfurt).

In our experiments, participants viewed a stimulus that contained a grating. In
each trial of the experiment two gratings were displayed in quick succession.

The first grating might look something like this:

![Surrounded grating](img/surrounded.png)

While the second would *always* look like this:

![Comparison grating](img/comparison.png)

In each trial of the experiment, participants had to say which of the gratings
(the first grating, or the second grating) had higher contrast.

> ## Contrast and surround suppression {.callout}
> While our visual system is not particulary good at identifying and
> discriminating the precise luminance or brightness of a stimulus, it is very
> sensitive to small changes in contrast. That is, to small *differences* in
> luminance across the image.
> Grating stimuli, like the one we used, are often used in vision science to
> probe this sensitivity. This is a way for us to measure the effects
> of the presencee of a surround on contrast perception. For example, it is well
> known that the relative orientation of the surround affects the degree to
> which the surround reduces the perceived contrast of the central patch.
> If the surrounding grating is parallel to the stimulus (as in the case shown
> above; also sometimes called 'co-linear'), it has a stronger effect on the
> perceived contrast (the contrast appears lower, just by virtue of the presence
> of the grating!). If the surrounding grating is orthogonal to the central
> patch, the effect is still there, but it is much weaker.
>
> If you are wondering why we are interested in surround suppression in the
> first place, you can find some of our papers using these measurements on [my website](http://arokem.org/publications). For example, in
> [one study (pdf)](http://arokem.org/publications/papers/Yoon2010SS_MRS.pdf),
> we found that this measurement tells us about differences in brain chemistry
> between healthy people, and patients with schizophrenia.


Let's look at the experimental data from one participant. We have two files from
this one subject in csv files, ortho.csv and para.csv. As their names suggest
they come from two different runs of the experiment: one in which the
surrounding stimulus was oriented in the parallel orientation relative to the
center stimulus  and one in which the surrounding stimulus was orthogonal to the
center stimulus. The files contain three columns: contrast1 is the contrast in
the first interval, contrast2 is the contrast in the second interval and answer
is what the participant thought had higher contrast. We will use the function
`mlab.csv2rec` to read the data into a numpy [record array](reference.html#record array):

~~~ {.python}

from matplotlib import mlab
ortho = mlab.csv2rec('data/ortho.csv')
para = mlab.csv2rec('data/para.csv')

~~~

If you take a look at the data you will see that the contrast in the second
interval was always 0.3 (30% contrast). That's because this stimulus served as a
reference stimulus, to help participants as an anchor. In other experiments, we
also varied that, but, for the purpose for our analysis here, we can safely
ignore that column altogether and only look at the contrast in the first
interval. Let's take a look at the data. First, we are just going to plot the
raw data as it is. We will consider the contrasts as our independent variable,
and the responses as the dependent variables.

~~~ {.python}

fig, ax = plt.subplots(1)
# We apply a small vertical jitter to each point, just to show that there are multiple points at each location:
ax.plot(ortho['contrast1'], ortho['answer'] + np.random.randn(len(ortho)) * 0.02 , '*')
ax.plot(para['contrast1'], para['answer'] + np.random.randn(len(para)) * 0.02 , '+')
ax.set_ylim([0.9, 2.1])
ax.set_xlabel('Contrast 1')
ax.set_ylabel('Which stimulus had higher contrast? (1 or 2)')

~~~




> ## Modeling in your field {.challenge}
>
> Give an example of data that you use in your research and a model applied to
> the data.
