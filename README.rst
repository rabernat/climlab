================
climlab
================
----------
 Python package for process-oriented climate modeling
----------

Author
--------------
| **Brian E. J. Rose**
| Department of Atmospheric and Environmental Sciences
| University at Albany
| brose@albany.edu

Installation
----------------
``python setup.py install``

    or, if you are developing new code

``python setup.py develop``


About climlab
--------------
``climlab`` is a flexible engine for process-oriented climate modeling.
It is based on a very general concept of a model as a collection of individual,
interacting processes. ``climlab`` defines a base class called ``Process``, which
can contain an arbitrarily complex tree of sub-processes (each also some
sub-class of ``Process``). Every climate process (radiative, dynamical,
physical, turbulent, convective, chemical, etc.) can be simulated as a stand-alone
process model given appropriate input, or as a sub-process of a more complex model.
New classes of model can easily be defined and run interactively by putting together an
appropriate collection of sub-processes.

Most of the actual computation for simpler model components use vectorized
``numpy`` array functions. It should run out-of-the-box on a standard scientific
Python distribution, such as ``Anaconda`` or ``Enthought Canopy``.

New in version 0.3, ``climlab`` now includes Python wrappers for more
numerically intensive processes implemented in Fortran code (specifically the
CAM3 radiation module). These require a Fortran compiler on your system,
but otherwise have no other library dependencies.  ``climlab`` uses a compile-on-demand
strategy. The compiler is invoked automatically as necessary when a new process
in created by the user.

Currently, ``climlab`` has out-of-the-box support and documented examples for

- 1D radiative and radiative-convective single column models, with various radiation schemes:
    - Grey Gas
    - Simplified band-averaged models (4 bands each in longwave and shortwave)
    - One GCM-level radiation module (CAM3)
- 1D diffusive energy balance models
- Seasonal and steady-state models
- Arbitrary combinations of the above, for example:
    - 2D latitude-pressure models with radiation, horizontal diffusion, and fixed relative humidity
- orbital / insolation calculations
- boundary layer sensible and latent heat fluxes


Example usage
------------------
The directory ``climlab/courseware/`` contains a collection of IPython / Jupyter
notebooks (*.ipynb) used for teaching some basics of climate science,
and documenting use of the ``climlab`` package.
These are self-describing, and should all run out-of-the-box once the package is installed, e.g:

``jupyter notebook Insolation.ipynb``


History
----------------------
The first versions of the code and notebooks were originally developed in winter / spring 2014
in support of an undergraduate course at the University at Albany.
See the original course webpage at
http://www.atmos.albany.edu/facstaff/brose/classes/ENV480_Spring2014/

The package and its API was completely redesigned around a truly object-oriented
modeling framework in January 2015.

It was used extensively for a graduate-level climate modeling course in Spring 2015:
http://www.atmos.albany.edu/facstaff/brose/classes/ATM623_Spring2015/
Many more examples are found in the online lecture notes for that course:
http://nbviewer.jupyter.org/github/brian-rose/ClimateModeling_courseware/blob/master/index.ipynb

Version 0.3 was released in February 2016. It includes many internal changes and
some backwards-incompatible changes (hopefully simplifications) to the public API.
It also includes the CAM3 radiation module.


Contact and Bug Reports
----------------------
Users are strongly encouraged to submit bug reports and feature requests on
github at
https://github.com/brian-rose/climlab


License
---------------
This code is freely available under the MIT license.
See the accompanying LICENSE file.
