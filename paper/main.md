---
# Ensure that this title is the same as the one in `myst.yml`
title: How the Scientific Python ecosystem helps answer fundamental questions of the Universe
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

<!-- ## Notes

* Example Jupyter notebook of simplified particle physics data analysis: [Zee_demo.ipynb](https://gitlab.cern.ch/gstark/pycolumnarprototype/-/blob/py_el_tool_test/Zee_demo.ipynb)
* Last public talk on international conference by the speaker: [11th Edition of the Large Hadron Collider Physics Conference (22-26 May 2023): HL-LHC and Beyond Computing Challenges](https://indico.cern.ch/event/1198609/contributions/5370078/)
* Dataset information: the until the date of the conference the ATLAS Collaboration plans to release a large amount of public dataset, so those data will be used for the talk material. If this is not achieved by the collaboration,for any reason, the talk will use already public simulated data. -->
