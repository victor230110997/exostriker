
**T**ransit and **R**adial velocity **I**nteractive **F**itting tool for **O**rbital analysis and **N**-body simulations : **The Exo-Striker** 

<p align="center">
  <img width="400" src="https://github.com/3fon3fonov/trifon/blob/master/lib/UI/33_striker.png">
</p>
 
The Exo-Striker analyzes exoplanet orbitals, performs N-body simulations, and models the RV stellar reflex motion caused by dynamically interacting planets in multi-planetary systems. It offers a broad range of tools for detailed analysis of transit and Doppler data, including power spectrum analysis for Doppler and transit data; Keplerian and dynamical modeling of multi-planet systems; MCMC and nested sampling; Gaussian Processes modeling; and a long-term stability check of multi-planet systems. The Exo-Striker can also perform Mean Motion Resonance (MMR) analysis, create fast fully interactive plots, and export ready-to-use LaTeX tables with best-fit parameters, errors, and statistics. It combines Fortran efficiency and Python flexibility and is cross-platform compatible (MAC OS, Linux, Windows). 

![new_es](/lib/png/Exo_striker_demo_image.png)


**WARNING!** This tool is under active development, and its functionality is enhanced on a daily basis! Use it at your own risk!

Also, please keep in mind that this software is developed mostly for my needs and fun. I hope, however, that you may find it capable of solving your scientific problems, too. 

What works:

* RV period search: via GLS periodogram & maximum lnL periodogram (MLP).
* Activity index period search via GLS periodogram.
* Transit period search via TLS.
* Keplerian and Dynamical RV modeling. 
* Transit photometry modeling.
* GP modeling (only SHO and Rot. GP "celerite" kernels integrated so far).
* Joint RVs + Transit + GPs best-fit optimization.
* Joint RVs + Transit + GPs MCMC/Nested Sampling (via "emcee" & "dynesty").
* TTVs and joint TTVs + RVs analysis.
* RV auto-fit (RV automated planet-finder algorithm).
* Fit for apsidal orbital precession, or apply GR precession. 
* Instant AMD stability check for multiple planetary systems.
* Long-term stability check of multiple planetary systems using SyMBA, MVS, and MVS with a GR precession.
* Various of minimization methods (via "SciPyOp").
* Fully interactive, super-fast, high-quality, exportable plots.
* RV vs. Activity time-series correlation analysis/plots.
* Import/Export of work sessions and multi-sessions. 
* Export plots to a matplotlib window for further customization.
* Export ready to use LaTeX tables with best-fit parameters, errors, and statistics. 
* Handy text editor and calculator tools.
* Multi-platform: It works on MAC OS (10.6+), Linux (Suse, Mint, Ubuntu, etc.) and Windows 10.
* Integrated Bash-shell (Linux only).
* Integrated Jupyter shell.
* Importable as a standard python library (i.e., ideal for scripting and notebooks, see "Examples").
* Print the GUI screen into a .jpeg image (useful for sharing quick results, just like the image above).

What is to be implemented:

* More GP kernels (work in progress). 
* Larger arsenal of N-body/dynamical simulation/analysis tools (+ REBOUND is planned to be included). 
* A photo-dynamical transit model.
* Internal TTV modeling (i.e. the external "TTVFast" will become a secondary option).
* A pip installer, and a ready-to-use pre-installed binary of the tool (work in progress). 
* Combined modeling with Astrometry.
* Documentation, Instructions, and Video tutorials (work in progress here: https://exostriker.readthedocs.io)


**Installation:**


**for a first download, just do:**

$ git clone https://github.com/3fon3fonov/exostriker  


**then, e.g. for an Ubuntu (Debian) installation:**

$ cd exostriker  
$ bash installers/linux_debian_install.sh  

**Successful installation should look like this:**

For which Python version we want to check/install packages?  
1) Python2  
2) Python3  
*#? 2*  

**(now it will check if you have the needed dependencies. If packages are missing it will ask you to install it")**

gfortran - yes!  
csh - yes!  
setuptools - yes!  
pip - yes!  
numpy - yes!  
scipy - yes!  
matplotlib - yes!  
PyQt5 - yes!  
PyQt5.QtSvg - yes!   
qtconsole - yes!   
jupyter - yes!   
pathos - yes!  
dill - yes!  
emcee - yes!  
corner - yes!  
celerite - yes!  
transitleastsquares - yes!  
dynesty - yes!  
rxvt - yes!  
batman - yes!   
ttvfast - yes!

*Installing the swift N-body lib, OK?  (you must, if you haven't done it already!)*
  
1) Yes  
2) No   
*#? 1*  

**(some output will be printed, it takes ~1 min.)**  
DONE
 

*Compiling the fortran fitting routines, OK? (you must, if you haven't done it already!)*
 
1) Yes  
2) No   
*#? 1*  
 
*Compiling Symba/mvs and other N-body routines, OK? (you must, if you haven't done it already!)*
 
1) Yes  
2) No   
*#? 1*   

**Thats it! Then simply:**

$ python es_gui.py

**to update the tool (inside the "exostriker" directory) just do:**

$ git pull  



**Also please read "README_for_installation"!**

I believe the installation instructions are very clear and easy to run.

If you still cannot boot the tool after a 'successful' installation, please try:

$ python es_gui.py -debug 

Then, copy the output error and please open a 'github' issue. Otherwise, all possible problems/bugs/crashes will be displayed on the 
'stdout/stderr' tab of the tool. If you use this tool and you find a bug or a problem, please report it!

A wish-list with your favorite tools and methods to be implemented is also welcome!
Just open an "Issue" on the GitHub, or send a PM to trifonov@mpia.de.



**Credit**

If you made the use of The Exo-Striker for your paper, I would appreciate if you give credit to it.
As it is unlikely that I will find time to write a refereed paper on the Exo-Striker soon, please cite the tool with its ASCL ID ascl:1906.004 (see https://ascl.net/1906.004).
 
The Exo-Striker relies on a number of open-source packages, which would be great if you 
acknowledge too. (if you had made the use of them):  


* The interactive plotting is done with a custom version of the "pyqtgraph": 

http://www.pyqtgraph.org/

* The transit modeling is done with "batman":
 
https://www.cfa.harvard.edu/~lkreidberg/batman/quickstart.html

* "GLS" and "MLP" periodograma are taken from Mathias Zechmeister's repo: 

https://github.com/mzechmeister/python

* "TLS" is taken from: 

https://github.com/hippke/tls

* MCMC sampling is done with "emcee": 

http://dfm.io/emcee/current/

* Nested Sampling is done with "dynesty": 

https://dynesty.readthedocs.io/en/latest/

* TTV models are adopted from "TTVfast-python":

https://github.com/mindriot101/ttvfast-python

* The "Text editor" used in the tool is a hack between "Megasolid Idiom" 
and "PyEdit2":

https://github.com/mfitzp/15-minute-apps/tree/master/wordprocessor

https://github.com/Axel-Erfurt/PyEdit2'

* N-body tests are performed using a custom version of the "Swift" N-body library,
modified by Man Hoi Lee (HKU) and Trifon Trifonov (MPIA).

https://www.boulder.swri.edu/~hal/swift.html

* Additionally, the Exo-Striker uses many "standard" Python libraries like 
"matplotlib", "numpy", "scipy", "dill", and more.



