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

In a Jupyter notebook, first, we will show how to load particle physics data in Python using the library [uproot](https://github.com/scikit-hep/uproot5).
Using the library [awkward](https://github.com/scikit-hep/awkward), the data will be cleaned to remove defects and only relevant data will be selected for further analysis.
Afterwards, some required corrections will be computed and applied to the data.
Those corrections are computed by specialized custom C++ libraries, which have been exposed to Python using [nanobind](https://github.com/wjakob/nanobind).
The main quantity that the Higgs boson manifests itself on the data, the so-called invariant mass, will be computed and plotted in a histogram using [numpy](https://github.com/numpy/numpy).
[Matplotlib](https://github.com/matplotlib/matplotlib) will be used to visualize the histogram and numpy to extract some basic statistical measures.
The whole workflow will be horizontally scaled using [dask](https://github.com/dask/dask) and especially using the native native dask collection for awkward arrays, [dask-awkward](https://github.com/dask-contrib/dask-awkward).
We will demonstrate how dask scaling greatly reduces the time to insight.
With this contribution the audience will have the chance to hear a story of how the open-source Scientific Python ecosystem is helping one of the largest international scientific collaborations in history to address its domain-specific problems and advance our understanding of the Universe.
The talk is targeting a wide spectrum of scientists, with no prior knowledge in particle physics, who analyze large amounts of domain-specific data.
It serves as a demonstration that solutions based on the Scientific Python ecosystem can well tackle problems that thus far had been addressed by specialized software without compromise on performance.
Furthermore, library developers will have the chance to see how their products are being utilized for real scientific applications at scale.

### Notes

* Relevant paper: [Columnar data analysis with ATLAS analysis formats | EPJ Web of Conferences](http://dx.doi.org/10.1051/epjconf/202125103001)
* Example Jupyter notebook of simplified particle physics data analysis: [Zee_demo.ipynb](https://gitlab.cern.ch/gstark/pycolumnarprototype/-/blob/py_el_tool_test/Zee_demo.ipynb)
* Last public talk on international conference by the speaker: [11th Edition of the Large Hadron Collider Physics Conference (22-26 May 2023): HL-LHC and Beyond Computing Challenges](https://indico.cern.ch/event/1198609/contributions/5370078/)
* Dataset information: the until the date of the conference the ATLAS Collaboration plans to release a large amount of public dataset, so those data will be used for the talk material. If this is not achieved by the collaboration,for any reason, the talk will use already public simulated data.

:::{include} introduction.md
:::

:::{include} scientific-python-ecosystem.md
:::

:::{include} uncovering-higgs.md
:::

## Uncovering the Higgs boson

_I thought we can use a simplified Higgs boson analysis as an example. This can be done either by using old open data as in AGC $H \to ZZ^*$ example ([notebook](https://agc.readthedocs.io/en/latest/atlas-open-data-hzz/HZZ_analysis_pipeline.html#ATLAS-Open-Data-H\rightarrow-ZZ^\star-with-ServiceX,-coffea,-cabinetry-&-pyhf)) or by using recent PHYSLITE Open Data. **PHYSLITE Open Data have NOT been released by ATLAS yet.**_

_We should pedagogically introduce the Higgs boson and its decay to Z bosons and eventually leptons. Additionally, we should talk about the backgrounds, which in this case originate from the simultaneous production of two Z boson that each one decays to a pair of same-flavour opposite-sign leptons. Additionally, backgrounds could be induced by jets faking leptons, thus processes as Z+jets or $t\bar{t}$ production can contribute as well._

### Loading data

_`uproot` and `awkward` usage to load particle physics data into jagged arrays_

### Cleaning and selecting data

_If we start from PHYSLITE data one needs to apply some lepton quality criteria (e.g. ID, isolation, etc.). AGC data will be probably cleaned already but we can still describe. Data selection refers to something like 4 leptons that have the same flavour in pairs and each pair has sum of charge 0. This selection will reflect the decay channel described above._

### Measurement uncertainties

_Here we can introduce the notion of experimental systematic uncertainties to account for imperfect knowledge of the ATLAS detector. This is the time to talk about how we used `nanobind` to port legacy C++ tools in Python._

_We need to think how to demonstrate that. It might only makes sense if we start from PHYSLITE data but I am not so sure...To simplify things we can show nominal plus and up and a down variation. This will look like three histograms as Matthias has showed in the [Zee_demo.ipynb](https://gitlab.cern.ch/gstark/pycolumnarprototype/-/blob/py_el_tool_test/Zee_demo.ipynb)._

### Feature engineering

_This is a fancy term for calculating the 4-lepton invariant mass which will be used as a discriminant. We can briefly expand on the usage of ML techniques to calculate more convolved discriminants in complex realistic analyses._

### The money plot

_Here we show the m(4l) distribution. We use `matplotlib`. To further advertise [Scikit-HEP](https://scikit-hep.org/) we can also introduce and use the `hist` and `mplhep` libraries._

_In order to plot different physics processes we need to properly weight them. I don't think worths spending time on this on the text though._

_Could we do some basic statistics with `pyhf`?_

_The point here is that signal is apparent on top of background._

### Scaling out

_Here we can talk about how scaling using `dask` can help us reduce the time to insight. I think we can use some outcomes of the recent 200Gbps challenge if we cannot run this ourselves. Although we could get something to run on from Alex H._

## Conclusion
