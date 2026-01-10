---
title: Modeling of Systems
nav_order: 3
---
# Modeling of Systems
In order to control a system, one needs to understand how a system behaves. This can be done best by the means of mathematical models of the system/plant that is to be controlled.

## What kind of mathematics can be used for describing a plant?
In control engineering there exist two main approaches to describing models of plants:
- Modeling in the Laplace/Frequency-Domain, using transfer function (Predominantly used in Classic Control)
- Modeling in the Time-Domain, using e.g. a state-space model (Predominantly used in Modern Control)

Each of these methods brings different advantages and disadvantages. While modern control focusses mainly on time-domain modeling, the frequency-domain provides incredibly useful intuition.

## How can these models be obtained?
There exist three main ways of obtaining such models.
### Mathematical Modeling
By writing down the governing (differential) equations of a system a mathematical model can be obtained. For electric systems Kirchhoff's laws are often utilized and for mechanical systems Newton's second law can often be used. This works very well on paper and often gives a good intuition for the system. However, sometimes are two complex to be modeled or there is a high uncertainty in the parameters or the systems governing equations are unknown. Consequently, obtaining a mathematical model straight away cannot always be done.

For this reason, there are two more typical ways to obtain a model.

### Observe system's response to a time-domain input
Another way to estimate a plant's model is to apply a time-domain input (like, for example a step or ramp) and then observe the dynamics of the output/variable of interest.


### Observe system's response to a frequency-domain input
The idea is similar to the previous approach. Some system's models can be obtained by applying sinusoidal (control) signals to it and then looking at the phase and magnitude of the output variable. From this a Bode-plot can be drawn, from which one can obtain an estimate of the underlying transfer function.
# Basic Terminology in System Modeling
## Static and Dynamic Systems
### Static Systems
A system is static if the output at time $t$ only depends on the the input at time $t$. 
$$
y(t)=3*u(t)
$$
$$
y(t)=u(t)^2
$$
where $u$ is the control signal and $y$ is the output, for example, are static systems. However, in real (engineering) life it is rarely that simple.
In the real world, systems often are dynamic.
### Dynamic Systems
Real systems rarely depend only on the input $u$ at time $t$. Take, for example:
$$
y(t) = \frac{du}{dt} \simeq \frac{u(t)-u(t-\delta)}{\delta}
$$
This system does not just depend on the input given at time $t$, but also on the input given before.

&rarr; Any differential equation represents a dynamical system!
## Linearity
A system is linear if it satifies the ***superposition property***.

Meaning, if you have, for example, two inputs $u_1(t)$ and $u_2(t)$ that would result in system outputs $y_1(t)$ and $y_2(t)$, respectively. Applying a linear combination of these inputs, would result in a similar linear combination of the outputs:
$$
\alpha * u_1(t)+\beta * u_2(t) \rarr \alpha * y_1(t)+\beta * y_2(t) 
$$

In other words, if a system satisfies the ***superposition property***, one can calculate its output, by adding up the systems responses to the individual inputs. 

Another useful property that linear systems have is the so-called ***homogenity property***. This property simply implies that if the input $u$ is scaled by a constant, the new output of the system is scaled by the same constant.
Meaning, if the system can be described as $y(t) = u(t)$, multiplying $u(t)$, by a constant, $\alpha*u(t)$, will result in $\alpha*y(t)$.


The previous example ($y(t)=u(t)^2$), for instance, is nonlinear, because:

$$
y(t)=(u_1(t)+u_2(t))^2 \neq u_1(t)^2+u_2(t)^2
$$
Consequently, it does not fulfill the superposition property.

Linerarity, generally, makes life easier in control and analysis of systems. And you will see that often even non-linear systems can be approximated as linear (under certain conditions and/or assumptions) using linearization techniques.

General indicators for ***non-linear systems***:
- Multiplication of input $u$ and output $y$

- Powers of output variable $y$, like $y^2$.
- Trigonometric functions, like sine or cosine

## Time-Invariance
A system is said to be time-invariant, if its model does not depend directly on time. A clear indicator for time-variance is, if the term $t$ appears directly in the systems equation.
For example, if an electric motor's strength decreases with battery voltage, the model of the system will be time-variant. However, often systems can be assumed time-invariant.

Most of classical control builds on linear and time-invariant systems.
# Basic Modeling of Electro-Mechanical Systems
Regardless of whether the model is obtained in the frequency-domain or time-domain, modeling usually starts by writing the governing equations of the system.






