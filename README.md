# Modified-Boussinesq-Solver-for-Power-law-Fluids
A slightly modified solver for solving mixed/forced convection flows for non newtonian Incompressible Laminar power law fluids


Note: The Temperature Equation in the Orignal Boussinesq solver for OpenFOAM V6 is solved by modelling the alpha(Diffusivity) as nu()/Pr, while this works for newtonian fluids, the moement your viscosity is dependant on shear rates as in the case of many power law models, this equation fails.
Therefore I have modelled the solver to take in more parameters to solve the Temperature Equations according to the formulatino in common literature.

The addtional parameters in the transport properties dictionary are kref, Scf
kref is the same as k(base viscosity) used in the power law model kref has to be given as an input by the user in the transport properties dictionary
Scf is the scaling factor equaling (Uinf/Lref)^n-1, where n is the power law index, Scf has to be given as an input by the user in the transport properties dictionary
