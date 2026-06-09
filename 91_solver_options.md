---
title: "Solver Options"
source: "Strand7 R246 API Manual"
pages: 1064–1070
---

# Solver Options

- `ptPlateStressVsStrain` — Stress vs strain.
- `ptPlateYieldVsTemp` — Yield vs temperature.

Brick Property Table Types

- `ptBrickModVsTemp` — Modulus vs temperature.
- `ptBrickAlphaVsTemp` — Expansion coefficient vs temperature.
- `ptBrickConductVsTemp` — Conductivity vs temperature.
- `ptBrickCpVsTemp` — Specific heat vs temperature.
- `ptBrickModVsTime` — Modulus vs time.
- `ptBrickConductVsTime` — Conductivity vs time.
- `ptBrickStressVsStrain` — Stress vs strain.
- `ptBrickYieldVsTemp` — Yield vs temperature.






The solvers can be launched by the Strand7 API using the functions St7RunSolver and
St7RunSolverProcess. The following lists the solver types and solver modes. The solver
modes determine how the solver is launched – it may be launched with the full window
as expected during normal solver runs with Strand7, it may be launched to only display a
small window with a progress bar or, alternatively, it may be launched without displaying
any window at all.

Solver Types

- `stLinearStaticSolver` — Linear static solver.
- `stLinearBucklingSolver` — Linear buckling solver.
- `stNonlinearStaticSolver` — Nonlinear static solver.
- `stNaturalFrequencySolver` — Natural frequency solver.
- `stHarmonicResponseSolver` — Harmonic response solver.
- `stSpectralResponseSolver` — Spectral response solver.
- `stLinearTransientDynamicSolver` — Linear transient dynamic solver.
- `stNonlinearTransientDynamicSolver` — Nonlinear transient dynamic solver.
- `stSteadyHeatSolver` — Steady heat solver.
- `stTransientHeatSolver` — Transient heat solver.
- `stLoadInfluenceSolver` — Load influence solver.
- `stQuasiStaticSolver` — Quasi static solver.

Solver Modes

smNormalRun - Full solver dialog is displayed, process waits for manual termination.
smNormalCloseRun - Full solver dialog is displayed, process terminates on completion.
smProgressRun - Solver progress bar is displayed, process terminates on completion.
smBackgroundRun - No solver dialog is created, process terminates on completion.




Result Types

hrNodeFlux - Node heat flux.
hrBeamFlux - Beam heat flux.
hrPlateFlux - Plate heat flux.
hrBrickFlux - Brick heat flux.

frBeamForcePattern - Beam force pattern.
frBeamStrainPattern - Beam strain pattern.
frPlateStressPattern - Plate stress pattern.
frPlateStrainPattern - Plate strain pattern.
frBrickStressPattern - Brick stress pattern.
frBrickStrainPattern - Brick strain pattern.

srNodeReaction - Node reaction.
srNodeVelocity - Node velocity.
srNodeAcceleration - Node acceleration.
srBeamForce - Beam force.
srBeamMNLStress - Beam MNL stresses.
srBeamStrain - Beam strain.
srPlateStress - Plate stress.
srPlateStrain - Plate strain.
srBrickStress - Brick stress.
srBrickStrain - Brick strain.
srElementNodeForce - Element node force.





Logical Solver Parameters

- `spDoSturm` — Sturm check.
- `spNonlinearMaterial` — Nonlinear material option.
- `spNonlinearGeometry` — Nonlinear geometry option.
- `spAddKg` — Use Kg option.
- `spCalcDampingRatios` — Calculate damping ratios.
- `spIncludeLinkReactions` — Include link reactions.
- `spFullSystemTransient` — Full system option for transient solution.
- `spNonlinearHeat` — Nonlinear option for heat solution.
- `spLumpedLoadBeam` — Lumped beam loads.
- `spLumpedLoadPlate` — Lumped plate loads.
- `spLumpedLoadBrick` — Lumped brick loads.
- `spLumpedMassBeam` — Lumped beam mass.
- `spLumpedMassPlate` — Lumped plate mass.
- `spLumpedMassBrick` — Lumped brick mass.
- `spForceDrillCheck` — Force drilling check.
- `spSaveRestartFile` — Save restart file option.
- `spSaveIntermediate` — Save sub-increments option.
- `spExcludeMassX` — Exclude mass X component.
- `spExcludeMassY` — Exclude mass Y component.
- `spExcludeMassZ` — Exclude mass Z component.
- `spSaveSRSSSpectral` — Save SRSS spectral results.
- `spSaveCQCSpectral` — Save CQC spectral results.
- `spDoResidualsCheck` — Perform residuals check.




- `spSuppressAllSingularities` — Suppress all singularities.
- `spSaveModalResults` — Save modal results.
- `spSpectralReactionAsInertia` — Set node reactions as inertia force.
- `spReducedLogFile` — Generate reduced log-file.
- `spIncludeRotationalMass` — Include rotational mass components.
- `spIgnoreCompressiveBeamKg` — Do not include KG terms for compressive beams.
- `spAutoScaleKg` — Auto scale KG terms.
- `spAutoShift` — In natural frequency analysis, allow frequency shift if rigid body
movement detected.

- `spSaveTableInsertedSteps` — Save results at steps at defined points in tables.
- `spSaveLastRestartStep` — Only keep last complete load increment in restart file.
- `spAutoAssignPathDivisions` — Uses a number of load-path divisions appropriate for
the specified time-steps.

- `spDoInstantNTA` — Establish quasi-static initial stress state for Creep problems.
- `spAllowExtraIterations` — Allow extra nonlinear iterations beyond
spMaxIterationNonlin when solution is convergent.

- `spPredictImpact` — Insert extra time-steps at contact activation events.

Integer Solver Parameters

- `spTreeStartNumber` — Tree start number.
- `spNumFrequency` — Number of modes for natural frequency solution.
- `spNumBucklingModes` — Number of modes for linear buckling solution.
- `spMaxIterationEig` — Maximum number of iterations for an eigenvalue
(buckling/frequency) solution.

- `spMaxIterationNonlin` — Maximum number of iterations for a nonlinear solution.
- `spNumBeamSlicesSpectral` — Number of beam slices to be generated for spectral
results.





- `spMaxConjugateGradientIter` — Maximum number of PCG iterations.
- `spMaxNumWarnings` — Maximum number of log-file warnings.
- `spFiniteStrainDefinition` — Strain definition; 0, 1 or 2 for Nominal, Engineering or
Green’s strains, respectively.

- `spBeamLength` — Nonlinear beam length formulation; 0 for Initial, 1 for Update.
- `spFormStiffMatrix` — Nonlinear stiffness matrix formation option; 0, 1, 2 or 3 for At
every iteration, First two iterations, First iteration or Automatic, respectively.

- `spMaxUpdateInterval` — Maximum number of iterations between stiffness matrix
formations.

- `spFormNonlinHeatStiffMatrix` — Nonlinear heat transfer matrix option; 0, 1or 2 for
At start of each row in the time step table, After every saved step or At every timestep,

respectively.

- `spExpandWorkingSet` — Additional modes included in sub-space iteration.
- `spMinNumViscoUnits` — Minimum number of visco-elastic creep units.
- `spMaxNumViscoUnits` — Maximum number of visco-elastic creep units.
- `spCurveFitTimeUnit` — Creep curve fit time unit, one of tuMilliSec, tuSec, tuMin,
tuHour or tuDay.

- `spStaticAutoStepping` — Static sub-stepping option; 0, 1, 2 or 3 for None, Load Scaling,
Displacement Scaling or Displacement Control (Arc Length), respectively.

- `spDynamicAutoStepping` — Dynamic sub-stepping option; 0, 1 or 2 for None, Time
Scaling or Displacement Scaling, respectively.

- `spBeamKgType` — Nonlinear beam Kg matrix calculation option; 0 for Simplified, 1for
Complete.

Double Solver Parameters

- `spEigenTolerance` — Eigenvalue tolerance.
- `spFrequencyShift` — Frequency shift.
- `spBucklingShift` — Buckling shift.
- `spNonlinDispTolerance` — Displacement tolerance.




- `spNonlinResidualTolerance` — Residual tolerance.
- `spTransientReferenceTemperature` — Reference temperature for transient solution.
- `spRelaxationFactor` — Relaxation factor.
- `spNonlinHeatTolerance` — Nonlinear heat tolerance.
- `spMinimumTimeStep` — Minimum time step size.
- `spWilsonTheta` — Wilson Theta number.
- `spNewmarkBeta` — Newmark Beta number.
- `spGlobalZeroDiagonal` — Matrix zero diagonal.
- `spConjugateGradientTol` — Conjugate gradient solver tolerance.
- `spMinimumDimension` — Minimum element dimension.
- `spMinimumInternalAngle` — Minimum element internal angle.
- `spZeroForce` — Zero point force factor.
- `spZeroDiagonal` — Zero matrix diagonal factor.
- `spZeroContactFactor` — Zero contact element factor.
- `spFrictionCutoffStrain` — Cutoff strain factor.
- `spZeroTranslation` — Zero translational displacement factor.
- `spZeroRotation` — Zero rotational displacement factor.
- `spMaxNormalsAngle` — Maximum plate normal angle.
- `spDrillStiffFactor` — Drilling stiffness multiplier.
- `spMaximumRotation` — Maximum allowable rotation.
- `spZeroDisplacement` — Zero displacement factor.
- `spMaximumDispRatio` — Maximum displacement ratio.
- `spMinimumLoadReductionFactor` — Minimum load increment reduction factor.
- `spMaxDispChange` — Maximum residual displacement change.
- `spMaxResidualChange` — Maximum residual force change.




