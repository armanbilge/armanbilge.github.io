---
layout: default
title: Research
---

# Research

Broadly, I am interested in developing computational methods to enhance our
    understanding of evolutionary processes.
In particular, I am eager to advance techniques for Bayesian phylogenetic
    inference.

## Cophylogeny Reconstruction <a href="//github.com/armanbilge/Cophy"><span style="font-size: 24px" class="mega-octicon octicon-mark-github"></a>

<center>
    <object type="image/svg+xml" data="cophylo.svg"></object>
</center>

Cophylogenies are systems of interdependent evolutionary trees and are relevant
    to models for coevolution between symbiotic organisms and genome evolution.
Specifically, a complete cophylogenetic history consists of a mapping of one
    evolutionary tree onto another and the sequence of biological events that
    generated this mapping (e.g., symbiotic host-switches or horizontal gene
    transfers).

Previous methods for cophylogenetic reconstruction generally attend to find the
    simplest explanation.
However, developing a probabilistic approach to this problem would enable
    reconstruction methods to consider more complex explanations as well as
    provide an idea of the statistical uncertainty.
The challenge is to find an efficient way to average over the infinite number of
    histories including unobserved events that result in the same observed
    history.

## Hamiltonian Monte Carlo <a href="//github.com/armanbilge/B3/tree/hamilton"><span style="font-size: 24px" class="mega-octicon octicon-mark-github"></a>

Bayesian phylogenetic inference involves sampling parameters for the
    evolutionary model according to their probability given the data.
This sampling is usually done with the Markov chain Monte Carlo (MCMC)
    algorithm.
We can imagine a frictionless skatepark where each point in the park corresponds
    to a particular set of parameter values for our model.
Specifically, we will design it such that parameter values with high probability
    map to points in the park with low elevation.
Then the MCMC algorithm looks like a random walk that moves through the park
    very slowly, thus making it an inefficient sampler.

Instead, we can place a skater in this park whose movement is given by Newton's
    laws of motion.
They will traverse the area efficiently by taking advantage of the features of
    the skate park.
The Hamiltonian Monte Carlo (HMC) algorithm is a sampler that uses this
    technique.
In my implementation of HMC for phylogenetics, it offers on average five times
    better performance than MCMC.

<center>
    <object width="480px" type="image/svg+xml" data="skatepark.svgz"></object>
</center>

I presented a [poster](//doi.org/10.6084/m9.figshare.1473743) on "Efficient
    Bayesian Evolutionary Analysis using Hamiltonian Monte Carlo" as a part of
    the symposium on *Untangling information, noise, and phylogenetic
    reconstruction in genome scale data* at SMBE 2015 in Vienna.

My work was partially supported by a Summer Scholarship from
    [The Allan Wilson Centre for Molecular Ecology and Evolution](//www.allanwilsoncentre.ac.nz).

<center>
    <object width="128px" type="image/svg+xml" data="awc.svg"></object>
</center>
