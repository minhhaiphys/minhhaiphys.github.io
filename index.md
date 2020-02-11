# Minh-Hai's GitHub Page


#### About me

I'm a scientist of an industrial research lab in nanotechnology and computing. My interests in programming are mainly on scientific data analyses, instrumentation (control software for measurements) and simulation. I code mostly in Python, can read (and write a bit) Julia, Matlab and C/C++.

Here are the projects (public domain) that I have been involved. Error reports and suggestions are most welcome.


### [PyMeasure](https://github.com/ralph-group/pymeasure)

How would you run a measurement from a computer? Some of you may choose to use LabView or Matlab, both are commercial software with expensive license fee, to set up a control program on the computer. When the measurement is completed and data collected, you run a separate program to analyze the data. From what you learn from the analyzed results, you will likely do a few more iterations of the measurement. Isn't it painful?

**PyMeasure** offers a free-of-charge solution to build a control program for your measurements, switching between running on a _Jupyter notebook_ (yes, programmers' favorite) and GUI without changing much of your codes. The package takes all the pain off your construction of a control program: it builds GUI and dynamic plots, it takes care of data collection, logging, and backup. What you need to do is specifying the overall procedure: which equipment does what, how the sweeps are to be executed. The rest will be automatic.

Furthermore, PyMeasure is written with Python. This means you can incorporate your data analyses into the control program, so that instead of seeing only the raw data when the experiment is running, as in the case of LabView and Matlab, with PyMeasure the program can analyze and display the result simultaneously with the execution, so you can choose to pause or abort the measurement whenever you're unhappy with the preliminary result.

Led by [Colin Jermain](https://github.com/cjermain) during our time in grad school at Cornell Univ. The package has been well maintained since then.


### [Auspex](https://github.com/BBN-Q/Auspex)

The PyMeasure package mentioned above targets convenience and peace of mind for novice programmers: it helps to quickly build a GUI program to run simple measurement sweeps. Think of it as an open-source replacement of LabView or Matlab. But if you want to run complicated measurements with irregular sweeps and collect a huge amount of data, then you need something more customizable. That is what Auspex offers.

**Auspex** allows you to construct measurements dynamically: Experiments can be dynamically modified depending on the outcome. If cleverly designed, this strategy can lead to large gain in speed (see the package _Adapt_ below). Data are stored in HDF5 binary format which can handle large data and is easily ported to Python. Auspex has been actively used by our group to run complicated qubit measurements.

Led by [Graham Rowlands](https://github.com/grahamrow) and other scientists in our group.


### [Adapt](https://github.com/BBN-Q/Adapt)

In physical experiments and numerical simulation, we often sweep one or more parameters, normally on a equally-separated grid. That can be inefficient. For instance, the most interesting features of a ferromagnetic resonance measurement are often found around the resonance frequency (which is unknown before the measurement). A sweep on a grid may be inefficient if most parts of the grid are far away from the resonance.

A more effective strategy for sweeping is to do it _adaptively_: First, run a quick sweep on a sparse grid with few data points. Then analyze the result from the first round, and decide whereabout to measure more. **Adapt** is a little package to help with this: It determines the points on the parameter space for the next round of measurement based on the results gotten so far, for example, the variation of the results.


### [PyWRspice](https://github.com/BBN-Q/pyWRspice)

**PyWRspice** is a Python wrapper for [WRspice](http://www.wrcad.com/) circuit simulator. It helps construct circuit schematics, render them to SPICE netlists, run them through _WRspice_ and read the outcome into Numpy arrays for further data processing. Hence, with PyWRspice, one can design, simulate circuits and analyze the results in a single Jupyter notebook. The big benefit of having all these tasks in one place is that one can optimize the circuit parameters by dynamically varying the parameters depending on the simulated results.

Some perks from PyWRspice: It can run multiple simulations in parallel using multi-core processor, and can run simulations on a remote server (via SSH connection).


### [PyESN](https://github.com/minhhaiphys/pyESN)

_Echo State Network (ESN)_ is a popular flavor of _Reservoir Computing_ which is a branch of _Recurrent Neural Networks_. The simplicity and effectiveness of ESN has been demonstrated in machine learning benchmarks involving _time-series data_ (audio, communications, etc), especially prediction tasks. Its internal dynamics motivates physicists to search for physical dynamical systems for its hardware implementation.

**PyESN** is a Python module for ESN, originally developed by [Clemens Korndörfer](https://github.com/cknd/pyESN). I revised the package to allow simulation of ESN with physical systems.

### [PySTDF](https://github.com/minhhaiphys/pystdf)

_STDF_ is a standard binary file format to store wafer, die and chip testing data in semiconductor industry. **PySTDF** is a Python parser to read STDF files, mostly developed by [Casey Marshall](https://github.com/cmars/pystdf) for Python 2. I ported it to Python 3 and added some extra features such as Excel extraction.

---

#### Links
* [Personal GitHub](https://github.com/minhhaiphys)
* [Work GitHub](https://github.com/BBN-Q)
* [Homepage](https://minhhaiphys.wordpress.com)
