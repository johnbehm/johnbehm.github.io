# Mop Joint Redesign

## Overview 
The Bona mop is used for cleaning and maintaining hardwood flooring. After just a couple of years, my first mop failed at a thin, filleted section near the joint between the handle and mop head, and now my second unit is showing similar signs of expected failure. I investigated the root cause and developed a redesigned geometry to reduce stress concentrations and improve durability. Using CAD modeling and finite element analysis, I evaluated the original design and iteratively refined the model, achieving over a 60% reduction in peak stress.

## Problem Definition
The mop head is connected to the handle via a double-pivoting joint, allowing for multi-axis motion. The failure occurred in the plastic component at the end of the handle, specifically at the protruding section where a pin connects it to the intermediate joint piece. This section is relatively thin (~1/4") with a small fillet radius (~1/32") at its base. This sharp transition creates a stress concentration under the bending loads applied during typical use. This repeated loading and stress concentration led to visible signs of material degradation, including discoloration and deformation (creep). Since my replacement mop is experiencing the same symptoms as my first mop, this suggests a design flaw rather than an isolated incident.

The objective of this project was to reduce stress concentrations in this critical section through a geometric redesign, which would improve the durability and lifespan of the component.

![Bona Mop Joint](../images/Bona Mop joint.JPG) ![Discoloration and Creep](../images/Bona Mop discoloration.JPG)

## Engineering Analysis
(text)

## CAD Model
![CAD Model of Original Piece](../images/Handle Piece.png)
![Side View](../images/Config 1.png)

## FEA Results
<video width="1280" height="720" controls>
  <source src="../images/Config 1 VM Stress.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>


## Iterations
![CAD Model of Configuration 2](../images/Config 2.png)
![Stress in Configuration 2](../images/Config 2 VM Stress.mp4)
![CAD Model of Configuration 3](../images/Config 3.png)
![Stress in Configuration 3](../images/Config 3 VM Stress.mp4)
![CAD Model of Configuration 4](../images/Config 4.png)
![Stress in Configuration 4](../images/Config 4 VM Stress.mp4)

## Results
(text)

## Key Takeaways
(text)
