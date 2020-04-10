# Getting Started with Global Sensitivity Analysis App for SimBiology Models

## Description
The Global Sensitivity Analysis App for SimBiology is a MATLAB application to compute Sobol indices and perform a multiparametric global sensitivity analysis (MPGSA) of model responses.

## Getting started
To install the app, double-click the mltbx file. You can manage installed add-ons by clicking the Add-Ons button on the MATLAB toolstrip.

To start the app, enter the following at the MATLAB command line: 
startGlobalSensitivityAnalysisApp(model), 
where model is a SimBiology model. 

For more information on how to apply doses and variants, enter: 
help startGlobalSensitivityAnalysisApp.

## Example
% Load model
model = sbmlimport('lotka');

% Configure model for simulation
configset = getconfigset(model);
configset.SolverOptions.AbsoluteTolerance = 1e-6;
configset.SolverOptions.RelativeTolerance = 1e-6;

% Define dose
dose = sbiodose('dose for y1', 'TargetName', 'y1', 'Amount', 50);

% Start the app for model with dose
startGlobalSensitivityAnalysisApp(model, dose);

## System Requirements
MATLAB version R2019b or later and the SimBiology (TM) toolbox are required.
Unit conversion is supported in MATLAB version R2020a or later.

## Features
Compute sampling based first and total order Sobol indices for model responses.
See also https://www.mathworks.com/help/simbio/ref/sbiosobol.html.

Perform a targeted sensitivity analysis using the multiparametric global sensitivity analysis (MPGSA) method.
See also https://www.mathworks.com/help/simbio/ref/sbiompgsa.html.

## References
Saltelli, Andrea, Paola Annoni, Ivano Azzini, Francesca Campolongo, Marco Ratto, and Stefano Tarantola. ?Variance Based Sensitivity Analysis of Model Output. Design and Estimator for the Total Sensitivity Index.? Computer Physics Communications 181, no. 2 (February 2010): 259?70. https://doi.org/10.1016/j.cpc.2009.09.018.

Tiemann, Christian A., Joep Vanlier, Maaike H. Oosterveer, Albert K. Groen, Peter A. J. Hilbers, and Natal A. W. van Riel. ?Parameter Trajectory Analysis to Identify Treatment Effects of Pharmacological Interventions.? Edited by Scott Markel. PLoS Computational Biology 9, no. 8 (August 1, 2013): e1003166. https://doi.org/10.1371/journal.pcbi.1003166.