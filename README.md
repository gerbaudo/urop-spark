Construction of a spark chamber to visualize cosmic rays
==========

This document describes the construction of a spark chamber particle
detector for educational purposes.

Davide Gerbaudo (dgerbaud@uci.edu), October 2013.

**Table of Contents**

- [What is a spark chamber](#sparkchamber)
- [What are cosmic rays](#cosmic)
- [Overview of the project](#overview)
- [Possible project subdivision](#subdivision)
  - [Construction of a spark chamber detector](#constructionspark)
  - [Construction and evaluation of a high-voltage pulser circuit](#constructionpulse)
  - [Implementation of an FPGA trigger logic](#constructiontrigger)


<a name="sparkchamber"/>
## What is a spark chamber

A spark chamber
([wikipedia](http://en.wikipedia.org/wiki/Spark_chamber)) is a
particle detector. It allows to detect and visualize subatomic
particles that costitute all the matter that surround us (including
ourselves!). In some way, a spark chamber is the ancestor of the
particle detectors that, for example, are used at the Large Hadron
Collider where the Higgs boson was recently discovered.

<a name="cosmic"/>
## What are cosmic rays

The particles that one can visualize with a spark chamber are
fundamental particles. We call them *fundamental* because we believe
that they cannot be broken down into smaller pieces. They are so small
that we usually do not see them in our everyday life, because we only
see the bigger objects in which the fundamental particles aggregate,
such as atoms and molecules. However, sometimes these particles can
move at a very large speed, and they can travel lonely without
aggregating into atoms.  For example, the particles produced in the
stars in outer space, can travel at relativistic speeds until they
reach us. We call them cosmic rays
([wikipedia](http://en.wikipedia.org/wiki/Cosmic_ray)), and they
continuosly hit our planet. In fact, if you keep your hand horizontal,
there are a few cosmic rays going through it every second.

The goal of this project is to build a spark chamber to visualize
these cosmic rays, to learn how we can detect these particles, and to
learn about particle physics.

<a name="overview"/>
## Overview of the project

In this section we briefly illustrate the main parts that need to
be built for this project.

The spark chamber is essentially set of parallel metal plates in a
gas-filled volume. When the particle goes through the gas, it breaks
up some of the gas atoms, creating pairs of negatively-charged
electrons and positively-charged ions. Because these two have opposite
charges, they attract each other, and quickly recombine into
atoms. This happens within microseconds. However, if a large electric
field is applied to the metal plates before the electrons and ions
recombine, then the electrons are accelerated by the electric field,
and they hit other atoms, which produce other electrons, and the
overall result is that one can see a little spark right where the
original cosmic muon was. You can see this for example on these videos
on youtube
([link](http://www.youtube.com/results?search_query=spark+chamber)).

However, for this to happen, one needs to

1.  have the metallic plates positioned at the right distance, and the
gaps filled with an appropriate gas; this involves the construction of
the **spark chamber** itself.

2.  apply to the plates a high voltage very quickly; this involves the
construction of a **high-voltage pulse generator**.

3.  only apply the high voltage when there actually a cosmic muon;
this involves the construction of a **trigger system**.

The chamber can be built as a plexiglass box with aluminum plates in
it. The box has to be transparent, so that we can see the sparks, and
air tight, so that we can fill it with gas. The gas will be a mixture
of 30% Helium 70% Neon. The tightness of the box is very important
because we want to avoid air infiltrations. The box should also have
the necessary valves allowing to fill it with gas and then seal it. It
should also have the necessary electrical connections to connect the
metallic plates and apply the high voltage.

The high-voltage pulse generator has to provide an 8000 V potential
within less than 500ns from a 'start' signal. Modern commercial
solutions do exist, but they are very expensive (usually above
$1000). Instead we want to investigate two more affordable solutions.
The first one is based on a circuit that can be built from cheaper
electronic components, and that is based on the spark plug used in
automobile engines. The second solution is based on the thyristor, an
electronic tube that was used in early radios and radars before the
advent of solid state devices. Thyristors are still available on the
market, mostly as collectibles, and we know that models such as the
PL5C22 would provide the necessary voltage and current required for
our detector.

The trigger system is a circuit that can determine within nanoseconds
whether a cosmic muon has gone through our spark chamber. The idea is
to have two simpler particle detectors (scintillators) one above and
one below the spark chamber. Each one of them can provide a small
electronic signal when a particle goes through it. The trigger system
should compute whether the signal from the top detector is followed by
a signal from the bottom detector within the very short time that it
takes to the cosmic ray to traverse the spark chamber. Remember that
cosmic rays travel almost at the speed of light. In the past, these
circuits had to be built from basic electronic
components. Fortunately, today there are generic circuits, called
field programmable gate arrays (FPGA), that can be programmed to
perform this kind of tasks. We want to implement our trigger system
with an FPGA.


The project can be summarized with the following scheme:

![Project scheme](images/project_scheme.png)

<a name="subdivision"/>
## Possible project subdivision

<a name="constructionspark"/>
### Construction of a spark chamber detector

What you do:

- design and build the box, the precision spacers, the plates, and
  their interconnections

- install gas valves and high-voltage electrical connections

Tricky parts:

- make the box air-tight

- avoid sharp edges on the metal (they cause spurious sparks)

What you learn:

- how a gas particle detector works (similar detectors are used for
  example in particle physics and in medical physics)

Tentative budget

| Item                                           | Price|
|------------------------------------------------|-----:|
| Six acrylic sheets, 12in x 12in, 1in thick     |  $200|
| Six aluminum sheets, 12in x 12in, 0.05" thick  |   $40|
| K-Bond Transparent Penetrating Acrylic Adhesive|   $30|
| Electrical connectors (check more precisely)   |  $100|
| Gas valves and fittings                        |   $50|
| Gas mixture (50L)  (perhaps smaller bottle?)   |  $500|
| Total                                          | $1020|

<a name="constructionpulse"/>
### Construction and evaluation of a high-voltage pulser circuit

What you do:

- design an build an analog fast circuit from simple components
  (resistor, capacitors, trasnformer, spark plug)

- determine whether the same functionalities can be obtained with an
  existing component (thyristor)

Tricky parts:

- build an high-voltage fast-switching circuit without discharges
  among its components (need proper insulation on the circuit)

- get the thyristor to work

What you learn:

- principles of analog electronic design, functioning of thyristor
  used in radars and PET medical devices

Tentative budget

| Item                                           | Price|
|------------------------------------------------|-----:|
| High voltage cables                            |  $200|
| Thyristor+socket                               |  $150|
| Spark plug, spacer, and support                |  $200|
| Support structrure, insulating glue            |  $100|
| Electronic components (breadboards, etc.       |  $200|
| Total                                          |  $850|

<a name="constructiontrigger"/>
### Implementation of an FPGA trigger logic

What you do:

- program a FPGA-based development board to implement a coincidence
  counting circuit

- the FPGA can do many other things, so the limit here is your
  imagination. For example, one could implement an online
  histogramming for the time of arrival of cosmic rays.

Tricky parts:

- convert the signals from the scintillators to electronic levels that
  can be processed by the FPGA

- implement the trigger logic in a flexible way, so that the
  interesting parameters (delay, time window duration, etc.) can
  easily be re-configured ad tuned

What you learn:

- how to program in Verilog, and how to use an FPGA; these modern
  devices are used everywhere, from your car to telecommunications

Tentative budget

| Item                                           | Price|
|------------------------------------------------|-----:|
| Digilent Nexys3 (Spartan-6) development board  |  $230|
| Electronic components (breadboards, etc.)      |  $200|
| Total                                          |  $430|

## Conclusion

The construction of a spark chamber detector to visualize cosmic muon
is a project in which at least three undergraduate students can
participate.  The students would have the possibility to learn a
diverse set of skills, and build an object that can then be used for
educational purposes. The visualization of fundamental particles with
this device is a nice way to demonstrate to non-specialist some of the
most fascinating aspects of cutting edge research in particle physics.
