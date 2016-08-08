Papers about network dynamics
++++++++++++++++++++++++++++++++++


ways to understand connectivity
===================================

Obtaining accurate connectivity is complex.

DTI and fMRI
--------------



electron microscopy, photostimulation, and electrophysiological recordings
-----------------------------------------------------------------------------


simulation: parameter scans
-----------------------------



advantages of structural plasticity
====================================

1. simulate a network without accurate connectivity parameters

2. give insights to how connectivity is generated or deleted during learning, memory

3. understanding how healing happens after lesion

4. understanding how a structure arise during critical periods



structural plasticity
=====================================

What is structural plasticity?
--------------------------------

an appropriate model of structural plasticity incorporates the dynamic generation, deletion, and rewiring of synapses within a network. The basic idea is **the plasticity in cortical networks is mainly driven by the need of individual neurons to homeostatically maintain their average electrical activity**. Additionally, a minimum level of activity is needed to form synaptic elements at all. If activity falls below this level, the neuron will remove synaptic elements too.

rules
----------

small network of 100+ or 1000+ neurons robustly grow towards a stabl homeostatic equilibrium of activity and connectivity.

all cell types had different desired average firing rate.


supported evidence: rewiring after lesion. (etweenness centrality?)


simulating structural plasticity with NEST (1): algorithms
------------------------------------------------------------

update in electrical activity and intracellular calcium concentration: intracellular calcium concentration is updated according to the electrical activity.
(resolution: each neuron on a ms timescale)

.. math::
   \frac{\mathrm{d}Ca}{\mathrm{d}t} = \begin{cases} -\frac{Ca(t)}{\tau}+\beta & \qquad \text{if the neuron fires}\\
                                                    -\frac{Ca(t)}{\tau}  & \qquad \text{otherwise}      
   \end{cases}
