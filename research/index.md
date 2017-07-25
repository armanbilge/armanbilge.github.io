---
layout: default
title: Research
---

# Research

Broadly, I am interested in developing computational methods to enhance our understanding of evolutionary processes.
In particular, I am eager to advance techniques for Bayesian phylogenetic inference.

## Hamiltonian Monte Carlo for Phylogenetics

<center>
  <video width="100%" autoplay loop>
    <source src="hmc.mp4" type="video/mp4"/>
    <source src="hmc.ogg" type="video/ogg"/>
  </video>
</center>

In Bayesian phylogenetic inference, instead of selecting a single "best" tree we create a sample of trees where the more likely a tree is to be correct, the more frequently it occurs in this sample.
This sampling is usually done with the Markov chain Monte Carlo (MCMC) algorithm.

To understand how sampling algorithms work, we can imagine a frictionless skatepark where every position represents a phylogenetic tree (both its shape and branch lengths).
Specifically, we will design the park such that trees with high probability correspond to positions with low elevation.
Then the MCMC algorithm looks like a random walk that moves through the park very slowly, thus making it an inefficient sampler.

Instead, we can simulate the motion of a skater in the park, occasionally pushing them in a random direction.
By periodically recording their position we create a sample of phylogenetic trees.
Notice that the skater can easily move long distances and take advantage of features of the park:
for example, if they are going uphill, this means that they are "exploring" lower probability trees and gravity will start pulling them back towards the high probability trees at the bottom of the park.

This sampling technique is known as Hamiltonian Monte Carlo (HMC).
While HMC has been successfully applied to other statistical problems, to extend the algorithm to Bayesian phylogenetics [we](http://matsen.group) introduced the following ideas:

1. An arrangement of skate parks, each representing all possible branch lengths for a particular tree topology
2. A probabilistic "jump" to enable the skater to move randomly between neighboring skateparks
3. Artificial smoothing of the park to increase the accuracy of our simulations

In the video above, each colored curve on the graph is a separate skatepark representing a different tree topology.
As the skater moves within and between the parks, the corresponding tree is shown on the right.

<a href="http://proceedings.mlr.press/v70/dinh17a.html"><span class="octicon octicon-file-text"></span> Our paper in ICML</a><br/>
<a href="//github.com/armanbilge/phyloHMC"><span class="octicon octicon-mark-github"></span> Source code for my implementation</a><br/>
<a href="//www.youtube.com/watch?v=Vdas0hNneMo"><span class="octicon octicon-device-camera-video"></span> My talk at Evolution 2016</a><br/>
<a href="//doi.org/10.5281/zenodo.814272"><span class="octicon octicon-graph"></span> My poster at Evolution 2017</a>
