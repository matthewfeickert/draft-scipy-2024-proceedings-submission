## Employing the Scientific Python ecosystem

<!-- _Here we can talk about how we used to do the event-loop analysis but we're shifting towards array programming models à la `numpy`.
We can describe our highly structured but jagged data and how domain specific languages, such as `awkward` (as a generalization of `numpy`) helps us deal with those peculiarities.
Maybe here we can also advertise the [Scikit-HEP](https://scikit-hep.org/) ecosystem._ -->

The multiple stages of physics data processing and analysis map onto different parts of the Scientific Python ecosystem.
This begins with the highly-structured but jagged nature of the event data structures in HEP.
The data structure of each event consists of variable length lists of physics object data structures (e.g. electrons, collections of tracks from charged objects).
This has traditionally motivated the use of event loops that implicitly construct event level quantities of interest and leveraged the `C++` compiler to produce efficient code, and made it difficult to take advantage of array programming paradigms that are common in Scientific Python given NumPy [@numpy] vector operations.
The Scikit-HEP library Awkward Array [@Awkward_Array_zenodo] provides a path forward by providing NumPy-like idioms for nested, variable-sized (JSON-like) data and also brings analysts into an array programming paradigm [@Hartmann:2021qzp].

With the ability to operate on HEP data structures in an array programming &mdash; or "columnar" &mdash; approach, the next step is to be able to read and write with the HEP domain specific ROOT [@Brun:1997pa] file format.
This is accomplished with use of the `uproot` library [@Uproot_zenodo], which allows for efficient transformation of ROOT files to NumPy or Awkward arrays.
The data is then filtered through kinematic and physics signature motivated selections using Awkward manipulations and queries to create array collections that contain the passing events.
Through intense detector characterization and calibration efforts, the ATLAS collaboration has developed robust methods and tooling to apply systematic corrections to the data (e.g. corrections to specific calorimeter subsystems).
Given the custom nature of the detector and correction implementations, these corrections are implemented in custom `C++` libraries in the ATLAS software framework, Athena [@ATL-SOFT-PUB-2021-001] [@Athena_zenodo].
