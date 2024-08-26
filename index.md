---
layout: default
math: true
---
#### [Nima Fazeli](https://www.mmintlab.com/people/nima-fazeli/)

<div style="text-align: right"> &copy; Nima Fazeli, 2024 </div>
<div style="text-align: right"> Last updated: 08-26-2024 </div>
<div style="text-align: right"> [How to cite these note](./cite.md), How to give feedback </div>

<br/><br/>

**Note**: These are working notes used for [a course being taught at the University of Michigan](https://intro2manipulation.robotics.umich.edu/). They will be updated throughout the Fall 2024 semester. 

### Table of Contents

1. Mechanics of Rigid-Body Frictional Interaction
2. Perception for Rigid-Body Frictional Interactions
3. Planning and Controls for Rigid-Body Interaction

### Preface

Robotic manipulation is the science and art of robotic systems interacting with their physical environments. In particular, manipulation is the controlled and purposeful physical interaction of the robot with its environment to produce desired effects and changes. Robotic manipulation represents a crucial advancement in the field of robotics, encompassing a wide array of tasks that enable robots to interact with and modify their surroundings. From delicate tasks such as picking up fragile objects to heavy-duty operations like assembling industrial components, robotic manipulation is the key that unlocks the potential for machines to perform tasks that were once limited to human dexterity and strength.

In the journey towards achieving adept robotic manipulation, researchers and engineers grapple with multifaceted challenges. A fundamental challenge lies in endowing robots with the sensory perception required to comprehend their environment. This involves developing advanced tactile, visual, and proprioceptive sensors that grant the robot a real-time understanding of the objects it interacts with. By acquiring this sensory data, robots can adjust their movements, forces, and grips with an astonishing level of precision, mirroring the human capacity for adapting to different scenarios.

Furthermore, the intricacies of robotic manipulation extend beyond sensorial comprehension. Planning and control algorithms play a pivotal role in enabling robots to perform tasks with efficiency and accuracy. These algorithms must take into account not only the physical properties of the objects being manipulated but also the dynamics of the robot itself. Balancing the forces exerted during a grasp, predicting the consequences of each movement, and optimizing trajectories are just a few examples of the computational challenges that arise in this domain.

Robotic manipulation is not confined to controlled environments or structured objects. The real world is rife with uncertainties, including variations in object shape, unexpected obstacles, and changes in the environment. As a result, manipulation strategies must be adaptive and resilient, capable of handling unforeseen circumstances without succumbing to errors or collisions.

As robotics continues to integrate with diverse industries such as manufacturing, healthcare, and logistics, the significance of robotic manipulation becomes increasingly apparent. Automation of intricate tasks leads to enhanced productivity, reduced labor costs, and improved safety. In medical applications, robots can perform delicate surgeries with enhanced precision, minimizing invasiveness and recovery times. In warehouses, robots adept in manipulation can swiftly sort, pick, and pack items, streamlining supply chains and expediting deliveries.

In this journey into the realm of robotic manipulation, this exploration aims to delve into the principles, technologies, and breakthroughs that underpin this evolving field. From the mechanics of grippers to the algorithms orchestrating graceful movements, each component contributes to the grand narrative of empowering robots with the ability to not only interact with their environment, but to masterfully manipulate it. As we navigate the intricacies of this dynamic landscape, the potential for innovation is vast, and the implications for industries and society at large are transformative.

The purpose of these notes is to introduce some of the key concepts, mathematics, tools, and algorithms prevalent in manipulation. These notes are used in teaching ROB599/ROB498 ``Introduction to Robotic Manipulation'', a new course taught at the University of Michigan. The field of robotic manipulation is very broad with a thriving and active research community. Our notes will touch on a small slice of this exciting field and continue to evolve to fill the needs of the material taught at an introductory level. This course is greatly influenced by Prof. Matt Mason's [The Mechanics of Robotic Manipulation](https://direct.mit.edu/books/monograph/3869/Mechanics-of-Robotic-Manipulation) and Prof. Russ Tedrake [Robotic Manipulation](https://manipulation.csail.mit.edu/index.html). Please contact Prof. Nima Fazeli at __nfz@umich.edu__ for any feedback, suggestions, and corrections to these notes.

### To be removed
Here is an inline one: \\( \sqrt{3x-1}+(1+x)^2 \\) how about \\[ x=y \\] and finally $ x = z $.

**The Cauchy-Schwarz Inequality**

$$\left( \sum_{k=1}^n a_k b_k \right)^2 \leq \left( \sum_{k=1}^n a_k^2 \right) \left( \sum_{k=1}^n b_k^2 \right)$$

