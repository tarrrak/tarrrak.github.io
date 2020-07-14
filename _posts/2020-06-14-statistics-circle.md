---
layout: post
title: Statistics on a circle
subtitle: short introduction to directional statistics
tags: [directional statistics, circular mean, periodic data]
comments: true
---
In everyday life we present a lot of data (like temperatures, stock indexes, average salary), which are conclusions of experiments and observations. To simplify the results we use mean values and confidence intervals. That is a great and simple approach which helps us to deal with large amounts of data. But some of the standard quantities fail when we deal with circular data. Napisz, że rzadziej się je spotyka i przykłady sa głupie. Dodaj Eulera i przykłady. 
## Standard approach
Let’s recall definitions of arithmetic mean:

$$ \bar{x} = \sum_i^N x_i $$

and standard deviation:

$$ \sigma = \sqrt{\frac{\sum_{i=1}^N (x_i-\bar{x})^2}{N}}. $$

Can we use these quantities on a circle? Not always. When we deal with well localized data, we can, because periodicity is negligible. But when the data are spread over on the whole circle it becomes more complicated. One simple way to visualize the problem is checking the distance between two points. Because of periodic boundary conditions points ‘see’ each other from both sides (fig). 
Fig
Sure, we can choose the shortest arc, but it complicates the definition of the distance. Such approach leads to violation of triangular inequality (fig).
Fig

## Circular quantities and distributions
Fortunately, there is a way to solve some of the problems. The branch of mathematics, which deals with periodic data is called directional statistics. Now, we will introduce so-called circular quantities and show some interesting properties. 
First, we take into consideration analogous of arithmetic mean. Let’s compute 2 dimensional center of mass and project it onto the circle. It is so-called circular mean, which is given by the following formula

$$ \bar{x}_{\circ} = arg\left(\sum_{i=1}^N  e^{i x_i}\right). $$

{: .box-note}
**Note:** Here we use complex numbers, but one can write these formula with a bunch of sine and cosine functions. The circular mean converges to arithmetic one when points are well localized, i.e. they occupy only a small part of circumference. 

So-called circular variance can help us to decide whether the points are well localized or not. It is given by the following formula

$$ var_{\circ} = 1 - \frac{1}{N} \left|\sum_{i=1}^N  e^{i x_i}\right|.$$

If all of the points are grouped together, \\( var_{\circ}  = 0 \\) , which means that the 2D center of mass lies close to the circumference. It is harder to interpret the result when \\( var_{\circ}  \approx 1 \\). Uniformly distributed points or uniformly distributed groups of points can generate such a result. For example, let’s consider two groups at oposite sides of the circle or points distributed regularly.

## Uniform sampling
The simplest probability distribution is a uniform one. We will see some characteristic features and counterintuitive behavior. Firstly, we can see what happens when we try to recover central limit theorem. Because of periodic boundary conditions it is not possible to get a gaussian from compounding uniform distributions. We will only get uniform one.
Secondly, let’s consider position of 2D center of mass of sets of points. We perform a small numerical experiment. We sample many times sets of n points and calculate centers of masses. Here we see results for different number of points in a set. 

In the limit of \\( n \rightarrow \infty \\) we expect to get Rayleigh distribution. Computing position of the center of mass is just adding unit vectors and dividing the length by the number of vectors. Hence, it is an example of a random walk. Rayleigh distribution is related to distances for a 2 dimensional random walker.

Thirdly, there is another intrinsic difference between open 1D and periodic boundaries. We want to ask about probability distribution when we take into account relative distance between particles. Let's consider marginal distribution of a multidimensional probability

$$  \rho(x_N) = \int_0^{2 \pi} … \int_0^{2 \pi} dx_1 … dx_{N-1} \rho(x_1,…,x_N).  $$

We obtained a function of one variable. We need to modify the marginal distribution, when we know that points gather eagerly and we do not know where exactly. The simplest example:
delta(x1-x2)
wzór
It means that first particle we can find everywhere, but with respect to the second one it can choose only zero distance. Hence, we need to modify marginal distribution and 
Badly modified marginal distribution:

$$  \rho_{bad}(x_N) = \int_0^{2 \pi} … \int_0^{2 \pi} dx_1 … dx_{N-1} \rho(x_1,…,x_N - f(x_1,…,x_N)).  $$

Why is it bad? Come back to the aforementioned example of uniformly distributed points. Figures below shows the results for different number of points.
Figs
We expect uniform distribution while here we get bell-like curve, which is well localized – even for \\( n=100 \\).  Why is it so? 
To obey counter intuitive behavior it is just enough not to take into account one particle., so the equation holds

$$  \rho_{modified}(x_N) = \int_0^{2 \pi} … \int_0^{2 \pi} dx_1 … dx_{N-1} \rho(x_1,…,x_N - f(x_1,…,x_{N-1})).  $$


## But why is it useful?
In physics, interacting particles can form so-called soliton. It is an effect of attractive interactions between particles and they are likely to group in one place. So, when we take into account modified marginal distribution (_phys._ modified one particle density function), we can observe such shape
Fig
Without proper shift, we observe uniform distribution or aforementioned artificial peak.

## TLDR; Sum up
Be aware of periodic data. But do not worry, usually standard methods are enough, because effects of periodicity are negligible in everyday life. 

## Literature:
directional statistics
Euler?
Rayleigh distributions
examples? Physics?
