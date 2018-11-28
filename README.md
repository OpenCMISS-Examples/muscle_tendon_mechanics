# muscle_tendon_mechanics

Simulates the force transmission of a tendon induced by the stimulation of the corresponding muscle.
The muscle model is based on the multi-phyiscs model introduced by Heidlauf et al (2013,2014,2016,2017). The model consists of
  1.) a 3D continuum mechanical model based on the therory of finite elasticity, simulating macroscopic deformations and force transmission.
  2.) Embeded one dimensional fibres simulating the propagation of action potentials along the muscle fibres. Thereby the one dimensional monodmain equation is solved.
  3.) The non-linear reaction term of the monodomain equation, i.e., the membrane model, is coupled to a core model of the muscle cell describing the entire excitation-contraction coupling patway (e.g., calcium release from the sarcoplasmic reticuulum and cross-bridge cycling in the sarcomere).
Thereby all submodels are coupled to each other.

In contrast to the original model, the passive material behaviour (of both muscle and tendon) is simulated by a hyperelastic, isotroptic Ogden-type material. 

# Building the example 

The fortran version of the example can be configured and built with CMake::

  git clone https://github.com/OpenCMISS-Examples/muscle_tendon_mechanics
  mkdir build
  cd build
  cmake -DOpenCMISSLibs_DIR=/path/to/opencmisslib/install ../muscle_tendon_mechanics
  make

This will create the example executable "laplace_equation" in ./src/fortran/ directory.

# Running the example

Go to the main folder (muscle_tendon_mechanics) and run the example by
  ./../src/fortran/muscle_tendon_mechanics
  
Note that the example needs to be executed from the main folder, since it includes a subfolder with all the nessecary input files, i.e., the corresponding cellml model. Otherwise the path to the cellml-file (in the fortran example file) needs to be adapted.
  
# Visualising the results 

Results can be visualised within cmgui with the included file 'show.cmgui'. Note that the file was tested with cmgui version 2.7.

# Verifying the results

The expected results can be found in the corresponding subfolder.
