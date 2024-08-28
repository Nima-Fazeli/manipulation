---
layout: default
math: true
---

# Grasp Analysis

Grasping is a fundamental skill in manipulation and has broad application to many tasks. While the 
term *"grasping"* has many interpretations and definitions, here we will refer to an object 
rigidly held by the robot as a grasp. Specifically, the robot is permitted to make contact with the object 
at a known number of points and is only able to impart forces through these contacts. If the set of forces 
imparted to the object satisfy a set of requirements that we will study in this section, then the robot 
has successfully grasped the object. The goal of this section is to study the conditions under which a given
grasp is stable. This is referred to as **Grasp Analysis**. In later chapters, we will dedicate time to
**Grasp Synthesis**, where the goal is to compute a grasp rather than assume that one is given.

The robot can pick and place grasped objects and/or use them as tools to interact with its environment. 
A real-world example of a robotic system grasping objects autonomously is shown in Fig.~\ref{fig:chap1:arc}.

<figure>
<p align="center">
  <img src="figures/chapter-1-arc.png" />
</p>
<figcaption> 
  <b>Fig. 1:</b> Real-world grasping system -- Team MIT-Princeton's entry into the Amazon Robotics Challenge (2016-2017)
</figcaption>
</figure>

In this section, we will assume all bodies are rigid and that Coulomb friction holds. In the remainder of this 
section we will develop the grasp matrix, a fundamental tool in analyzing grasp quality, 
and draw connections to the contact Jacobian we have studied previously. We will then use the grasp matrix 
to evaluate form and force closures of grasps to evaluate the stability of grasps. These properties are central 
to the task of planning for and controlling grasps and we will touch on these in subsequent chapters. 

In the remainder, our analysis follows the excellent Grasping chapter of \citet{prattichizzo2016grasping} 
and we refer the reader to this text for further details.
