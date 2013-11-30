Below you can find a few links to reading material for the spark
chamber project. Please do not be intimidated by the long list; start
with the ones that interest you the most.

The thesis of Susan Richards ("The Design and Construction of a Spark
Chamber for Display Purposes") is a good starting point. It provides a
overview of the detector, and also fair amount of details on one of
its possible implementations. Most of the other documents focus on one
particular aspect of the project.

## Overview documents

- Susan Richards, "The Design and Construction of a Spark Chamber for
  Display Purposes", 1975. Senior thesis, Princeton University.
  [pdf](https://docs.google.com/file/d/0B3inNvIrVHvvWFNuZzFnYmZwZmM/edit?usp=sharing)
  This spark chamber is still working today:
  [picture](https://lh6.googleusercontent.com/-xEEBnr4i6Ys/Uhycv9IbLNI/AAAAAAAAAjA/2NlrVADsycU/w939-h704-no/spark_chamber_pu.jpg)
- W. A. Wenzel, "Spark Chambers", Annual Review of Nuclear Science
  Vol. 14: 205-238 1964. Review
  paper. [pdf](http://dx.doi.org/10.1146/annurev.ns.14.120164.001225) and [pdf2](https://drive.google.com/file/d/0B3inNvIrVHvvYUdGdkEtaVVOYTA/edit?usp=sharing)
  
## Similar setups at other universities

- **Birmingham**. Web page with several pictures, videos, and
  descriptions
  [link](http://www.hep.ph.bham.ac.uk/general/outreach/SparkChamber2/)

- **Cambridge**. Main web page with overview, pictures, and videos
  [link](http://www.hep.phy.cam.ac.uk/~lester/teaching/SparkChamber/SparkChamber.html)
  - P. de Grouchy. "Construction and evaluation of a fast switching
    trigger circuit for a cosmic ray detection spark chamber", 2009.
    Detailed description of the triggering circuit, and of the
    spark-plug circuit to generate the high-voltage
    pulse. [pdf](https://docs.google.com/file/d/0B3inNvIrVHvvMkxfSFVDenpkZFE/edit?usp=sharing)
    Some of the pictures are missing from the pdf; e-mail me
    (dgerbaud@) and I will send you the doc file.
  - J. Collins, "Construction of a Prototype Spark Chamber", 2010. Report and preprint, with several practical recommendations
    on the design of the chamber and of the electronics. [arxiv](http://arxiv.org/abs/1010.4010)
  - European Particle Physics Outreach Group
    [link](http://www.hep.phy.cam.ac.uk/~lester/teaching/SparkChamber/NIKHEF/eppog.web.cern.ch/eppog/Resources/SparkChamber.html)

- **Manchester**. Two wikis; in addition, each wiki has links to
  detailed reports written by each one of the students involved.
  - Wiki from 2012 with more details on the construction and budget
  [link](http://manchestermphys2012.wikispaces.com)
  - Wiki from 2013, with more details on the operations of the chamber
  (e.g. gas pressure, potential improvements, etc.)
  [link](https://uomsparkchamber2013.wikispaces.com)

- **Montana**. Web page of Prof. John Belz. Picures and schematics for
  the thyratron driver
  circuit. [link](http://www.physics.utah.edu/~belz/sparkchamber/sparkchamber.html)

- **NIKHEF**. Home page of Fred Hartjes. Extensive documentation,
  including manuals, engineering drawings, and electronic
  schematics. Some of the documents are in
  dutch. [link](http://www.nikhef.nl/~i56/)

- **Notre Dame**. Justin Pilot, "Design and Construction of a Narrow-Gap
  Spark Chamber for Detection of Cosmic Rays", 2006. Senior thesis
  team report. Review and overall description. Includes mechanical
  drawings of the metal plates and some electronic
  schematics. [link](https://docs.google.com/file/d/0B3inNvIrVHvvYVFJekNVTF9rem8/edit?usp=sharing)

- **Quarknet** project. Similar project to detect cosmic rays [link](http://quarknet.fnal.gov/)
  Schematics of their electronic board [link pdf](https://drive.google.com/file/d/0B3inNvIrVHvvOVhYajg5NVVVWDA/edit?usp=sharing)


At this link you can find a few more papers from the literature on
this subject:
[citeulike/gerbaudo/spark](http://www.citeulike.org/user/gerbaudo/tag/spark)

## High-voltage

Safety: [guidelines](http://www.repairfaq.org/sam/safety.htm)

Marx generators: 
- [Wikipedia](http://en.wikipedia.org/wiki/Marx_generator), 

- [quick and dirty marx generator](http://www.electricstuff.co.uk/marxgen.htm),

- [Avalanche transistor](http://www3.telus.net/schmaus2/elect/ftron.html),

- [MOS power transistor with thyratron](http://dx.doi.org/10.1016/0167-5087(84)90380-6),

- [wiki4hv](http://wiki.4hv.org/index.php/Category:High_Voltage),

- [A lightweight high-voltage PS](http://jnaudin.free.fr/html/lwhvps.htm) based on flyback,

- [Simple High Voltage Generator](http://www.repairfaq.org/sam/hvinvert.htm)

- [DSRD Russian design, 2010](http://dx.doi.org/10.1134/S0020441210020132)

Power supply makers: 
[Emco](http://www.emcohighvoltage.com/), [Spellman](http://www.spellmanhv.com)

## FPGA

We plan to use the Digilent Nexys 3 development board. On the Digilent
website you can find the board documentation
[link](http://www.digilentinc.com/Products/Detail.cfm?Prod=NEXYS3) and
you can download their software to simulate and program the board
[link](http://www.digilentinc.com/Products/Detail.cfm?Prod=ADEPT2).
Their software is available for both Linux and Windows.

The book [Free Range VHDL](http://www.freerangefactory.org/site/pmwiki.php/Main/Books)
provides a good introduction to the VHDL language used to
program FPGAs. It is an open-source book, you can download
the pdf. 

## UROP

We plan on submitting a group proposal. You can find the Fall 2013
call at this [link](http://www.urop.uci.edu/grants.html).

Please note that the deadline for submission is Monday, November 4th.
In addition to the group proposal "you must also upload the proposal
and a personal statement for each undergraduate group member."
