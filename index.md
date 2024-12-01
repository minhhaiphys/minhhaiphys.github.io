# Minh-Hai's GitHub Page

#### About me

I'm an R&D engineer in nanotechnology and computing. My programming interests are mainly in scientific simulation, numerical calculation, data analyses, and instrumentation (control software for measurements). I code primarily in Python and C++, some Matlab and JavaScript.

Below are some projects (in public domain) that I have been involved. I hope you find them useful. Error reports and suggestions are most welcome.


### [PyMacrospin](https://github.com/minhhaiphys/pymacrospin) - Magnetic simulation

A big part of the beauty and challenge of magnetization dynamics comes from its vector analysis. Vector differential equations are usually nonintuitive and difficult to manipulate. A good way to understand and gain intuition of magnetization dynamics is to visualize it by simulation.

**PyMacrospin** is a Python package to perform macrospin (i.e. standalone magnetization vector) simulation following the Landau-Lifshitz-Gilbert description of magnetization dynamics under an effective field and the Slonczewski spin-transfer-torque effect. The package provides simple interface to describe the sample (demag field, uniaxial and cubic anisotropy), spin-torque contribution, and sweep the external field and current for most frequently used measurement techniques. Beside the implementation using core Python, the package comes with Numba and Cython kernels to speed up the calculation by 100x.

Originally developed as [macrospin](https://github.com/ralph-group/macrospin) by [Colin Jermain](https://github.com/cjermain) in his time in grad school. I upgraded the package by adding core Python and Numba kernels.


### [PyWRspice](https://github.com/BBN-Q/pyWRspice) - Circuit simulation

**PyWRspice** is a Python wrapper for [WRspice](http://www.wrcad.com/) circuit simulator. It helps construct circuit schematics, render them to SPICE netlists, run them through _WRspice_ and read the outcome into Numpy arrays for further data processing. Hence, with PyWRspice, one can design, simulate circuits and analyze the results in a single Jupyter notebook. The big benefit of having all these tasks in one place is that one can optimize the circuit parameters by dynamically varying the parameters depending on the simulated results (see also the package _Adapt_ below).

Some perks from PyWRspice for heavy circuit simulation workload: It can run multiple simulations in parallel using multi-core processor, and can run simulations on a remote server (via SSH connection).

I wrote _PyWRspice_ for an internal project at Raytheon BBN. Fortunately it was made publicly available and has been used by people outside of the company.


### [PyMeasure](https://github.com/ralph-group/pymeasure) - Experiment automation with GUI

How would you run a measurement from a computer? Some of us may choose to use LabView or Matlab, both are commercial software with expensive license fee, to set up a control program on the computer. When the measurement is completed and data collected, one would run a separate program to analyze the data. From the analyzed results, one will likely do a few more iterations of the measurement. Isn't it painful?

**PyMeasure** offers a free-of-charge solution to build a control program for your measurements which can be executed on a _Jupyter notebook_ (yes, programmers' favorite) or with Qt GUI. The package takes all the heavy lifting from the construction of a control program: it builds GUI and dynamic plots, it takes care of data collection, logging, and backup. All you need to do is specifying the overall procedure: which equipment does what, how the sweeps are to be executed. The rest will be automatically handled by PyMeasure.

Furthermore, PyMeasure is written with Python. This means you can incorporate your data analyses into the control program, so that instead of seeing only the raw data when the experiment is running, as in the case of LabView and Matlab, with PyMeasure the program can perform post-processing and display the results concurrently with the execution, so you can choose to pause or abort the measurement whenever you're unhappy with the preliminary result.

Led by [Colin Jermain](https://github.com/cjermain) during our time together in grad school at Cornell Univ. The package has been well maintained since then and been used by many institutions (including my current company).


### [Auspex](https://github.com/BBN-Q/Auspex) - Automation for high-speed and complex experiments

The PyMeasure package mentioned above targets convenience and peace of mind for novice programmers: it helps to quickly build a GUI program to run simple measurement sweeps. Think of it as an open-source replacement of LabView or Matlab. But if you want to run fast, complicated measurements with irregular sweeps and collect a huge amount of data, then you need something more powerful and customizable. That is what Auspex offers.

**Auspex** was developed for automating high-speed, complex measurements in quantum computer engineering. It allows you to construct measurements dynamically: Next measurements can be dynamically modified depending on the outcome of the previous runs. If cleverly designed, this strategy can lead to huge gain in speed (see the package _Adapt_ below). Data are stored in HDF5 binary format which can handle large data and is easily ported to Python.

Led by [Graham Rowlands](https://github.com/grahamrow), my ex-boss at Raytheon BBN and the head of the QEC (quantum engineering and computing) group, and developed by the scientists and engineers in the group.


### [Adapt](https://github.com/BBN-Q/Adapt) - Optimization of recursive procedures

In physical experiments and numerical simulation, we often sweep one or more parameters, normally on a equally-separated grid. That can be inefficient. For instance, the most interesting features of a ferromagnetic resonance measurement are often found around the resonance frequency (which is unknown before the measurement). A sweep on a grid may be inefficient if most parts of the grid are far away from the resonance.

A more effective strategy for sweeping is to do it _adaptively_: First, run a quick sweep on a sparse grid with few data points. Then analyze the result from the first round, and decide whereabout to measure more. **Adapt** is a little package to help with this: It determines the points on the parameter space for the next round of measurement based on the results gotten so far, for example, the variation of the results.

I wrote the majority of _Adapt_ during my summer internship at Raytheon BBN.


### [PyESN](https://github.com/minhhaiphys/pyESN) - Custom recurrent neural network

_Echo State Network (ESN)_ is a popular flavor of _Reservoir Computing_ which is a branch of _Recurrent Neural Networks_. The simplicity and effectiveness of ESN has been demonstrated in machine learning benchmarks involving _time-series data_ (audio, communications, etc), especially prediction tasks. Its internal dynamics motivates physicists to search for physical dynamical systems for its hardware implementation.

**PyESN** is a Python module for ESN, originally developed by [Clemens Korndörfer](https://github.com/cknd/pyESN). I revised the package to allow simulation of ESN with physical systems.

### [PyENT](https://github.com/minhhaiphys/PyENT) - Random number benchmarking

A Python version of [FourmiLab's ENT](http://www.fourmilab.ch/random/): Benchmarking suite for pseudorandom number generator. It performs the following tests on random number sequence (read byte-per-byte from binary files): Entropy, Chi-square, Arithmetic mean versus Median, Monte-Carlo value for Pi, and Serial correlation coefficient.

### [PySTDF](https://github.com/minhhaiphys/pystdf)

_STDF_ is a standard binary file format to store wafer, die and chip testing data in semiconductor industry. **PySTDF** is a Python parser to read STDF files, mostly developed by [Casey Marshall](https://github.com/cmars/pystdf) for Python 2. I ported it to Python 3 and added some extra features such as Excel extraction.

---

#### Links
* [My Homepage](https://www.minhhai.me)
* [My GitHub](https://github.com/minhhaiphys)
* [Raytheon BBN-Q's GitHub](https://github.com/BBN-Q)

