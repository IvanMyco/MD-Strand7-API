---
title: "Beam Results"
source: "Strand7 R246 API Manual"
pages: 1073–1076
---

# Beam Results

Node Results
Reaction

[0..2] - Reaction forces in the 123 axis directions for the specified UCS.
[3..5] - Reaction moments about the 123 axis directions for the specified UCS.

Temperature

[0] - Temperature.

Flux

[0] - Heat flux.

Influence

[0..2] - Translational components in the 123 axis directions for the specified UCS.
[3..5] - Rotational components about the 123 axis directions for the specified UCS.





Beam results include force, stress, strain, release, cable position, flux, creep strain, strain
energy, beam displacement and beam reactions. The St7GetBeamResultArray,
St7GetBeamResultArrayPos, St7GetBeamResultEndPos, St7GetBeamResultSinglePos and
St7GetBeamReleaseResult functions can be used to access these result quantities.
Result quantities can be selected via a combination of the following inputs:

ResultType
The result type to be returned, one of rtBeamForce, rtBeamStrain,
rtBeamStress, rtBeamTRelease, rtBeamRRelease, rtBeamCableXYZ,
rtBeamFlux, rtBeamGradient, rtBeamCreepStrain, rtBeamEnergy, rtBeamDisp
or rtBeamNodeReact.

ResultSubType
The quantity sub-type, one of stBeamLocal, stBeamPrincipal or stBeamGlobal.
Results are returned in a one-dimensional array BeamRes which consists of contiguous
blocks of data. Each block corresponds to a location along the beam. The length
NumColumns of each block is also returned by the function as it depends on the
requested result quantity.
The number of these blocks is dependent on the function that is called – for example,
St7GetBeamResultSinglePos will return one such block, whereas St7GetBeamResultArray
will return an array containing NumStations such blocks.
Constants are provided that index specific result quantities within each block of data.
For example, the axial force at the ith beam station is stored in the location:

BeamRes[(i-1)*NumColumns+ipBeamAxialF]
These constants are specific to the result type requested – appropriate constants for
each result type are listed in the rest of this section.





Force Results for stBeamLocal and stBeamPrincipal

- `ipBeamSF1` — Shear force in the 1-axis direction.
- `ipBeamBM1` — Bending moment in the 1-axis direction.
- `ipBeamSF2` — Shear force in the 2-axis direction.
- `ipBeamBM2` — Bending moment in the 2-axis direction.
- `ipBeamAxialF` — Axial force.
- `ipBeamTorque` — Torque.

Force Results for stBeamGlobal

- `ipBeamFX` — Internal force in the Global X direction.
- `ipBeamMX` — Internal moment in the Global X direction.
- `ipBeamFY` — Internal force in the Global Y direction.
- `ipBeamMY` — Internal moment in the Global Y direction.
- `ipBeamFZ` — Internal force in the Global Z direction.
- `ipBeamMZ` — Internal moment in the Global Z direction.
At any cut section, the forces/moments are those required to keep End 2 of the beam in
equilibrium.

Stress

- `ipMinFibreStress` — Minimum fibre stress.
- `ipMaxFibreStress` — Maximum fibre stress.
- `ipMaxShearStress1` — Maximum shear stress in the 1-axis direction.
- `ipMaxShearStress2` — Maximum shear stress in the 2-axis direction.
- `ipAvShearStress1` — Average shear stress in the 1-axis direction.
- `ipAvShearStress2` — Average shear stress in the 2-axis direction.





- `ipTorqueStress` — Torsional stress.
- `ipMaxPrincipalStress` — Maximum principal stress.
- `ipMinPrincipalStress` — Minimum principal stress.
- `ipMinPipeHoopStress` — Minimum hoop stress.
- `ipMaxPipeHoopStress` — Maximum hoop stress.
- `ipMinAxialStress` — Minimum axial stress.
- `ipMaxAxialStress` — Maximum axial stress.
- `ipMinBendingStress1` — Minimum bending stress in the 1-axis direction.
- `ipMaxBendingStress1` — Maximum bending stress in the 1-axis direction.
- `ipMinBendingStress2` — Minimum bending stress in the 2-axis direction.
- `ipMaxBendingStress2` — Maximum bending stress in the 2-axis direction.
- `ipYieldRatio` — Portion of beam section that has yielded.

Flux

- `ipBeamFlux` — Heat flux.
- `ipBeamTempGradient` — Temperature gradient.

Strain

- `ipAxialStrain` — Axial strain.
- `ipCurvature1` — Curvature in the 1-axis direction.
- `ipCurvature2` — Curvature in the 2-axis direction.
- `ipTwist` — Twist.

Release

- `ipRelEnd1Dir1` — End 1 release in the 1-axis direction.





