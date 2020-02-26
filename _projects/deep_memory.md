---
layout: page_project
title: Deep Memory Hierarchies
date: 2019-01-29
updated:
navbar: Research
subnavbar: Projects
project_url:
status: running
topics:
  - storage
keywords:
head: bautista_gomez_l
members:
  - balasz_g
  - perarnau_s
  - ishikawa_y
---

## Research topic and goals

Deep Memory Hierarchies are an important part of future exascale systems and as
they come opening new opportunities, they also bring significant challenges to
the HPC world. In particular, it is not clear what is the best and more
efficient way to use such devices, how to position the data related to
performance metrics but also to reliability constrains is an open question. In
this project we investigate all these issues, from memory access patterns to
interfaces to easily handle multiple memory devices with different bandwidth,
latency and reliability characteristics.

## Results for 2019/2020

Following earlier successes in this collaboration on abstractions and
mechanisms for monitoring application memory accesses, we have shifted the work
to focus on the intersection of machine learning and memory management.

During his second visit to RIKEN, Aleix has investigated machine learning
workloads from a systems perspective. Specifically, he has been focusing on
memory management issues in pytorch and identified a number opportunities
for OS level performance improvement. This is an ongoing effort, which we
anticipate to lead to another joint publication.

Argonne and RIKEN are also working on another side of memory management: the
use of reinforcement learning in the control of the page placement of memory in
applications. We identified gem5, a cycle-accurate simulator, as the basis for
this work. We have prototyped the missing systems calls required for our
experiments in the gem5 emulation layer, and discussed how to connect with a
python distributed RL framework developed by RIKEN.

## Visits and meetings

Internship of Aleix Roca at RIKEN between November 2019 and February 2020,
under the supervision of Balazs Gerofi.

We schedule regular video meetings between members, and are meeting regularly
during scientific conferences (ICPP19, SC19, SIAM PP20).

## Impact and publications

{% bibliography --cited --file jlesc.bib %}


## References

{% bibliography --file external/deep-memory.bib %}