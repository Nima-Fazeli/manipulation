---
layout: default
math: true
---

## Dynamical Movement Primitives (DMPs)

Dynamical Movement Primitives (DMPs) are a powerful framework for representing and 
learning complex motor behaviors in robotics. Originally developed for learning and 
generalizing human motion, DMPs are particularly useful in robotic systems where 
adaptability and robustness to perturbations are required. In this section, we introduce 
DMPs in the context of point robots and explain the underlying principles.

## DMPs for Point Robots

A point robot is a simple representation of a robot where the configuration is specified 
by a position $\vec{x}(t) \in \mathbb{R}^n$, where $n$ is the dimension of the space 
(e.g., $n=2$ for a planar point robot). The goal of a DMP is to generate smooth trajectories 
for the robot to follow from an initial position $\vec{x}_0$ to a goal position 
$\vec{x}_g$ while allowing for flexibility and generalization in the movement.

### Canonical System

The key idea behind DMPs is to separate the time evolution of the system from the 
spatial component. To achieve this, DMPs introduce a \emph{canonical system} that acts as 
a phase variable, $s(t) \in [0,1]$, which monotonically decays over time. The canonical 
system is governed by the differential equation:

$$
\begin{equation}
    \dot{s}(t) = -\alpha_s s(t),
\end{equation}
$$

where $\alpha_s$ is a positive constant that controls the rate of decay. The canonical 
system ensures that the DMP formulation is time-invariant and can scale to different time durations 
for the task.

## Transformation System

The spatial part of the movement is handled by the \emph{transformation system}, which 
defines the desired trajectory for the point robot. The transformation system is defined 
by a second-order dynamical system:

$$
\begin{equation}
    \tau \ddot{\vec{x}}(t) = \alpha_x \left( \beta_x (\vec{x}_g - \vec{x}(t)) - \dot{\vec{x}}(t) \right) + f(s(t)),
\end{equation}
$$

where $\tau$ is a time-scaling constant, $\alpha_x$ and $\beta_x$ are positive constants 
that determine the stiffness and damping of the system, and $f(s(t))$ is a nonlinear forcing 
term that modulates the trajectory to achieve complex movements.

## Forcing Term

The forcing term $f(s(t))$ is a key component of the DMP framework, as it allows for the 
encoding of arbitrary movements. This term is typically represented as a linear combination 
of Gaussian basis functions:

$$
\begin{equation}
    f(s(t)) = \frac{\sum_{i=1}^N \psi_i(s) w_i}{\sum_{i=1}^N \psi_i(s)} s(t),
\end{equation}
$$

where $\psi_i(s) = \exp(-h_i (s - c_i)^2)$ are Gaussian kernels centered at $c_i$ with 
widths $h_i$, and $w_i$ are the corresponding weights. These weights are learned from 
demonstration data, allowing the DMP to replicate complex motions while maintaining a 
flexible and robust structure.

## Summary of DMP Properties

DMPs offer several desirable properties for motion generation in robotics:

- **Generalization:** DMPs can generalize a learned movement to different start and goal positions by adjusting $\vec{x}_0$ and $\vec{x}_g$.
- **Robustness:** DMPs naturally handle perturbations by following a stable attractor towards the goal position.
- **Time Invariance:** The separation of the canonical and transformation systems allows the same trajectory to be executed over different time scales.
- **Learning from Demonstration:** DMPs can be efficiently learned from a small number of demonstrations, making them practical for robot learning tasks.


In the next section, we will discuss how to implement DMPs for point robots in practice, and demonstrate their use in trajectory generation for different types of tasks.
