## Uncovering the Higgs boson

_I thought we can use a simplified Higgs boson analysis as an example.
This can be done either by using old open data as in AGC $H \to ZZ^*$ example ([notebook](https://agc.readthedocs.io/en/latest/atlas-open-data-hzz/HZZ_analysis_pipeline.html#ATLAS-Open-Data-H\rightarrow-ZZ^\star-with-ServiceX,-coffea,-cabinetry-&-pyhf)) or by using recent PHYSLITE Open Data.
**PHYSLITE Open Data have NOT been released by ATLAS yet.**_

_We should pedagogically introduce the Higgs boson and its decay to Z bosons and eventually leptons.
Additionally, we should talk about the backgrounds, which in this case originate from the simultaneous production of two Z boson that each one decays to a pair of same-flavour opposite-sign leptons.
Additionally, backgrounds could be induced by jets faking leptons, thus processes as Z+jets or $t\bar{t}$ production can contribute as well._

### Loading data

_`uproot` and `awkward` usage to load particle physics data into jagged arrays_

### Cleaning and selecting data

_If we start from PHYSLITE data one needs to apply some lepton quality criteria (e.g. ID, isolation, etc.).
AGC data will be probably cleaned already but we can still describe.
Data selection refers to something like 4 leptons that have the same flavour in pairs and each pair has sum of charge 0.
This selection will reflect the decay channel described above._

### Measurement uncertainties

_Here we can introduce the notion of experimental systematic uncertainties to account for imperfect knowledge of the ATLAS detector.
This is the time to talk about how we used `nanobind` to port legacy C++ tools in Python._

_We need to think how to demonstrate that.
It might only makes sense if we start from PHYSLITE data but I am not so sure...
To simplify things we can show nominal plus and up and a down variation.
This will look like three histograms as Matthias has showed in the [Zee_demo.ipynb](https://gitlab.cern.ch/gstark/pycolumnarprototype/-/blob/py_el_tool_test/Zee_demo.ipynb)._

### Feature engineering

_This is a fancy term for calculating the 4-lepton invariant mass which will be used as a discriminant.
We can briefly expand on the usage of ML techniques to calculate more convolved discriminants in complex realistic analyses._

### The money plot

_Here we show the m(4l) distribution.
We use `matplotlib`.
To further advertise [Scikit-HEP](https://scikit-hep.org/) we can also introduce and use the `hist` and `mplhep` libraries._

_In order to plot different physics processes we need to properly weight them.
I don't think worths spending time on this on the text though._

_Could we do some basic statistics with `pyhf`?_

_The point here is that signal is apparent on top of background._

### Scaling out

_Here we can talk about how scaling using `dask` can help us reduce the time to insight.
I think we can use some outcomes of the recent 200Gbps challenge if we cannot run this ourselves.
Although we could get something to run on from Alex H._