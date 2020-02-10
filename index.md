# Minh-Hai's GitHub Page

### About me:
I'm a scientist of an industrial research lab in nanotechnology and computing. My interests in programming are mainly on scientific data analyses, instrumentation (controlling software for scientific experiments) and simulation. My primary programming language is Python.

Here are the projects (public domain) that I have been involved:

### [PyMeasure](https://github.com/ralph-group/pymeasure)
How would you run a measurement from a computer? Some of you may choose to use LabView or Matlab, both are commercial software with expensive license fee, to set up a control program on the computer. When the measurement is completed and data collected, you run a separate program to analyze the data. From what you learn from the analyzed results, you will likely do a few more iterations of the measurement. Isn't it painful?

PyMeasure offers a free-of-charge solution to build a control program for your measurements, switching between running on a Jupyter notebook (yes, programmers' favorite) and GUI without changing much of your codes. The package takes all the pain off your construction of the control program: it builds GUI and dynamic plots, it takes care of data collection, logging, and backup. What you need to do is specifying the overall procedure: which equipment does what, how the sweeps are to be executed. The rest will be automatic.

Furthermore, PyMeasure is written with Python. This means you can incorporate your data analyses into the control program, so that:
* Instead of seeing only the raw data when the experiment is running, as in the case of LabView and Matlab, with PyMeasure the program can analyze and display the result simultaneously with the execution, so you can choose to pause or abort the measurement whenever you're unhappy with the preliminary result.
* You can do more than just staring at the result and pause then restart the measurement. Control programs built with PyMeasure are Python scripts, hence are completely scriptable: Experiments can be dynamically modified depending on the outcome. If cleverly designed, this strategy can lead to large gain in speed (see the package Adapt below).

Led by [Colin Jermain](https://github.com/cjermain) during our time in grad school at Cornell Univ. The package has been well maintained since then.

### [Auspex](https://github.com/BBN-Q/Auspex)
Led by [Graham Rowlands](https://github.com/grahamrow) and other scientists in our research group.


### [Adapt](https://github.com/BBN-Q/Adapt)


### [PyWRspice](https://github.com/BBN-Q/pyWRspice)


### [PyESN](https://github.com/minhhaiphys/pyESN)
Originally developed by [Clemens Korndörfer](https://github.com/cknd/pyESN) as a purely software Echo State Network. I revised the package to allow simulation of ESN with physical systems.

### [PySTDF](https://github.com/minhhaiphys/pystdf)
Mostly developed by [Casey Marshall](https://github.com/cmars/pystdf) for Python 2. I ported it to Python 3 and added some extra features such as Excel extraction.
