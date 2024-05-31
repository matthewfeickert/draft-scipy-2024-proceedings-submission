---
# Ensure that this title is the same as the one in `myst.yml`
title: How the Scientific Python ecosystem helps answering fundamental questions of the Universe
abstract: |
  The ATLAS experiment at CERN explores vast amounts of physics data to answer the most fundamental questions of the Universe.
  The prevalence of Python in scientific computing motivated ATLAS to adopt it for its data analysis workflows while enhancing users' experience.
  This talk will describe to a broad audience how a large scientific collaboration leverages the power of the Scientific Python ecosystem to tackle domain-specific challenges and advance our understanding of the Cosmos.
  Through a simplified example of the renowned Higgs boson discovery, attendees will gain insights into the utilization of Python libraries to discriminate a signal in immersive noise, through tasks such as data cleaning, feature engineering, statistical interpretation and visualization at scale.
exports:
  - format: pdf
    template: eartharxiv
    output: exports/scipy_proceedings_draft.pdf
---

## Copy over from proposal edit this

The [ATLAS experiment at CERN](https://atlas.cern/), in Geneva, Switzerland, studies subatomic particles to seek answers to the most fundamental questions of the Universe.
Due to the rarity of interesting subatomic phenomena, vast amounts of data are collected by the experiment.
Those data are further reduced but physicists still have to analyze hundreds of terabytes for their studies.
This has been traditionally conducted using experiment-specific custom C++ frameworks.

In recent years, there has been a broad community-driven shift towards the Scientific Python ecosystem inside of particle physics.
The use of dataframes and NumPy-like idioms for data analysis has enhanced the user experience while providing efficient computations without the need of coding optimized low-level routines.
This trend is followed by the education system too, as students learn python as the primary programming language.
Therefore, the ATLAS collaboration committed to extend and improve its data analysis paradigm by leveraging the Scientific Python ecosystem and its benefits.
Open-source libraries have been used to build domain-specific data analytics and visualization workflows.
Those libraries belong either to the general Scientific Python ecosystem or to the particle physics-specific [Scikit-HEP](https://scikit-hep.org/) ecosystem.
Furthermore, next generation C++/Python binding tools have been used to expose pieces of the legacy C++ code, which encapsulates decades of domain-specific development, to the Python environment.

The talk will briefly introduce the big data science conducted at CERN along with the commensurate amount of data produced and waiting for analysis.
The main objective of the talk will be to showcase how libraries from the Scientific Python ecosystem have been used to solve a common particle physics problem.
This problem is the discrimination of a signal of interest in immersive noise. Successfully tackling such a problem, the physicists of the ATLAS collaboration discovered the Higgs boson in 2012.
We will use as an example a simplified version of the data analysis workflow used for the Higgs boson discovery.
This example is selected because it contains all the usual steps a particle physics data analyst has to undertake to discriminate such a signal; data cleaning and selection, feature engineering, visualization and basic statistical interpretation.

### Notes

* Example Jupyter notebook of simplified particle physics data analysis: [Zee_demo.ipynb](https://gitlab.cern.ch/gstark/pycolumnarprototype/-/blob/py_el_tool_test/Zee_demo.ipynb)
* Last public talk on international conference by the speaker: [11th Edition of the Large Hadron Collider Physics Conference (22-26 May 2023): HL-LHC and Beyond Computing Challenges](https://indico.cern.ch/event/1198609/contributions/5370078/)
* Dataset information: the until the date of the conference the ATLAS Collaboration plans to release a large amount of public dataset, so those data will be used for the talk material. If this is not achieved by the collaboration,for any reason, the talk will use already public simulated data.

:::{include} introduction.md
:::

:::{include} scientific-python-ecosystem.md
:::

:::{include} uncovering-higgs.md
:::

:::{include} conclusions.md
:::

:::{include} acknowledgements.md
:::
