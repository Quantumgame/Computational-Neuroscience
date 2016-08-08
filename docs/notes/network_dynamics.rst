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

Step1: update in electrical activity and intracellular calcium concentration: intracellular calcium concentration is updated according to the electrical activity.
(resolution: each neuron on a ms timescale)

.. math::
   \frac{\mathrm{d}Ca}{\mathrm{d}t} = \begin{cases} -\frac{Ca(t)}{\tau}+\beta & \qquad \text{if the neuron fires}\\
                                                    -\frac{Ca(t)}{\tau}  & \qquad \text{otherwise}
   \end{cases}

where :math:`\tau` is the calcium decay constant and :math:`beta` is the calcium intake constant (how much calcium is accumulated each time the neuron fires).
(the calcium concentration and firing rate is linearly propotional to the average firing rate)

Step2: update synaptic element

synaptic elements: on axons (axonal boutons: senders of synaptic activity) or dendrites (spines: receivers of synaptic activity)

The growth speed of synaptic elements depends on the target calcium concentration, minimum concentration. (Z is the number of element)

linear:

.. math::
   \frac{\mathrm{d}z}{\mathrm{d}t}=v(1-\frac{1}{\epsilon}Ca(t))

Gaussian:

.. math::
   \frac{\mathrm{d}z}{\mathrm{d}t}=v(2e^{-\frac{Ca(t)-\xi}{\zeta}}-1)

where :math:`\xi = (\eta+\epsilon)/2`, :math:`\zeta=(\epsilon-\eta)/2\sqrt{\ln{2}}`, :math:`\eta` is the minimum amount of calcium concentration, and :math:`\epsilon` is the target calcium concentration.

When the Z value is increased (or decreased) by one, a new synaptic element is generated or is deleted.


Step3: update in connectivity

New elements allow the formation of new synapses, deleted elements lead to synapse breaking. Every available elemets has the same probability to be randomly chosen for a new connection. And once an element is deleted and a synapse is broken, the counterpart is released for a new connection. (enabling *rewiring*).
