---
layout: page
title: Linear Models
minutes: 10
---

# Linear models.

> ## Learning Objectives {.objectives}
>
> * Learners can identify a linear model.
> * Learners can use `scipy.stats` to fit a linear model to data

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

How do we choose $beta_i$?

Selecting a value for the parameters, $beta_i$ is called "fitting the model".
You might , but a common criterion is to select parameters that reduce the sum
of the square errors, relative to the data (SSE). That is, let:

$SSE = \sum{(y - \hat{y})^2}

And:

$\hat{y} = $

We will want to

It turns out that linear models are easy to fit. Under some fairly generic
assumptions (for example that $\epsilon$ has a zero-mean normal distribution),
there is actually an analytic solution to this problem. That is, you can plug it
into a formula and get the exact solution: the set of $\beta$ that give you the
smallest SSE between the data you collected and the function defined by the
parameters.

> ## Linearized models {.callout}
>  Because linear models are easy to fit, if you can transform your data somehow
>  to get it into a linear form, you should definitely do that.

Let's fit a linear model to our data. In our case, a linear model would
be a straight line in 2D:

$y = \beta_0 + \beta_1 x$

Where, $\beta_0$ is the intercept and $\beta_1$ is the slope.

To fit the model, we'll start using the `scipy` library.

## `Scipy`

This library contains many functions that are useful in a variety of scientific
computing tasks.

If you import the library, you will see that it is composed of a variety of
sub-modules, each devoted to a different set of algorithms, or a topic:


~~~ {.python}
import scipy
scipy?
~~~

~~~ {.output}

SciPy: A scientific computing package for Python
================================================

Documentation is available in the docstrings and
online at http://docs.scipy.org.

Contents
--------
SciPy imports all the functions from the NumPy namespace, and in
addition provides:

Subpackages
-----------
Using any of these subpackages requires an explicit import.  For example,
``import scipy.cluster``.

::

 cluster                      --- Vector Quantization / Kmeans
 fftpack                      --- Discrete Fourier Transform algorithms
 integrate                    --- Integration routines
 interpolate                  --- Interpolation Tools
 io                           --- Data input and output
 linalg                       --- Linear algebra routines
 linalg.blas                  --- Wrappers to BLAS library
 linalg.lapack                --- Wrappers to LAPACK library
 misc                         --- Various utilities that don't have
                                  another home.
 ndimage                      --- n-dimensional image package
 odr                          --- Orthogonal Distance Regression
 optimize                     --- Optimization Tools
 signal                       --- Signal Processing Tools
 sparse                       --- Sparse Matrices
 sparse.linalg                --- Sparse Linear Algebra
 sparse.linalg.dsolve         --- Linear Solvers
 sparse.linalg.dsolve.umfpack --- :Interface to the UMFPACK library:
                                  Conjugate Gradient Method (LOBPCG)
 sparse.linalg.eigen          --- Sparse Eigenvalue Solvers
 sparse.linalg.eigen.lobpcg   --- Locally Optimal Block Preconditioned
                                  Conjugate Gradient Method (LOBPCG)
 spatial                      --- Spatial data structures and algorithms
 special                      --- Special functions
 stats                        --- Statistical Functions

Utility tools
-------------
::

 test              --- Run scipy unittests
 show_config       --- Show scipy build configuration
 show_numpy_config --- Show numpy build configuration
 __version__       --- Scipy version string
 __numpy_version__ --- Numpy version string

~~~

To use any one of these sub-modules, we'll need to import it specifically. 
