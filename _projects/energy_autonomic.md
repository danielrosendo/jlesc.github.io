---
layout: page_project
title: Improving the Performance and Energy Efficiency of HPC Applications Using Autonomic Computing Techniques
date: 2018-04-17
updated:
navbar: Research
subnavbar: Projects
project_url:
status: running
topics:
  - architectures
keywords:
  - autonomic computing
  - energy efficiency
head: rutten_e
members:
  - perarnau_s
  - bleuse_r

---

## Research topic and goals

Behaviour of HPC systems, such as performance, power consumption, thermal
distribution, are increasingly hard to predict due to process variations and
dynamic processors, which conflicts with conventional bulk synchronous
parallelism software models such as MPI. Additionally computing facilities are
now interested in limiting computing resources by power/energy budget rather
than CPU time. Such idea is also negatively affected by unpredictable behaviour
of modern HPC systems. Hardware-level power-limiting capability is becoming a
standard feature in modern processors. Intel running average power limit
(RAPL), for example, adjusts CPU core frequency (and CPU states if needed)
periodically in order to limit the CPU power consumption not to exceed
user-specified per-socket power budget. While RAPL, in fact, is an excellent
mechanism for independent workloads, there are multiple considerations for HPC
usage. The side effect of such power limiting is performance variation between
cores/sockets/nodes; no mechanism to communicate between sockets or nodes. The
effective range of user-specifiable power budget is limited; lower efficiency
with lower power budget. They tend to be a hardware feature; not tuneable.

We propose a software-level solution to provide additional control mechanisms
that increase hardware power-limiting feature and work for multiple nodes by
applying autonomic computing techniques and targeting HPC workloads.  We adopt
an approach involving Autonomic Computing and Control Theory. We will identify
significant sensors and actuators (e.g., switching on/off cores, changing CPU
frequency), build adaptive models of the process to be controlled, and define
robust adaptive control objectives w.r.t. appropriate metrics. We will design
and experimentally validate controllers regulating consumption while ensuring
performance. We will explore variants, beyond simple threshold-based control
e.g., predictive control to avoid overshooting or adaptive control for
robustness to the natural variability, considering costs of actions, avoiding
oscillations and over-reaction, handle multiple criteria, coordinate multiple
autonomic loops. Based on our previous experience in Cloud-oriented Autonomic
Computing, we will generalize and explore novel issues in adapting our
approaches to specificities of HPC and power management.

## Results for 2019/2020

On the basis of the preliminary work done at ANL on instrumentation of HPC
applications, Inria has begun work on a range of controllers for the runtime
adaptation of the Power Cap level in RAPL. A first approach is considered,
re-using results on other work concerning a different problem (regulating the
degree of parallelism according to synchronization cost), but which could be
transferred here. Another approach involves measuring progress and power and
making decisions based on predictions.

Argonne completed the design and implementation of an infrastructure to perform
control experiments using jupyter notebooks. This infrastructure can be
deployed on a wide range of servers, and allows collaborators to independently
implement their own control algorithm using a simple interface and a high level
language. The notebook then connect remotely to the existing Argo NRM
infrastructure, that keeps track of actuators, sensors and application
management.

## Visits and meetings

We schedule regular video meetings between the different members of the
project.

{% person rutten_e %} visited ANL for two days to make progress on the project
on April 18-19 2019.

## Impact and publications

None yet.

{% bibliography --cited --file jlesc.bib %}

## Future plans

On the control of RAPL, short term plans are to finalize the design of some of
the controllers and their implementation, in order to integrate them in the
NRM platform for experimental evaluation. We then plan to consider more
elaborate control problems, e.g. taking into account variables other than
power in the system, and to consider more elaborate control techniques, to
obtain controllers that are more robust or give a more efficient use of the
system.

On a longer term, we plan to start working on another feedback loop approach
for HPC, at a higher-level than processor level : we believe that there are
opportunities in combining control-based methods and scheduling-based
techniques for the general problem of runtime allocation and placement.

## References

{% bibliography --file external/energy_autonomic.bib %}