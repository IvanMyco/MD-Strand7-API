---
title: "Plate Results"
source: "Strand7 R246 API Manual"
pages: 1077–1084
---

# Plate Results

Beam Results

- `ipRelEnd1Dir2` — End 1 release in the 2-axis direction.
- `ipRelEnd1Dir3` — End 1 release in the 3-axis direction.
- `ipRelEnd2Dir1` — End 2 release in the 1-axis direction.
- `ipRelEnd2Dir2` — End 2 release in the 2-axis direction.
- `ipRelEnd2Dir3` — End 2 release in the 3-axis direction.

Energy

- `ipBeamEnergyStored` — Stored energy.
- `ipBeamEnergySpent` — Spent energy.





Plate results include stress, strain, strain energy, force moment, curvature, ply stress, ply
strain, ply reserve, heat flux, temperature gradient, reinforcement design, creep strain,
soil characteristics, nodal reactions and user defined quantities. The
St7GetPlateResultArray function can be used to access these result quantities.
Result quantities can be selected via a combination of the following inputs:

ResultType
The result type to be returned, one of rtPlateStress, rtPlateStrain, rtPlateEnergy,
rtPlateForce, rtPlateMoment, rtPlateCurvature, rtPlatePlyStress,
rtPlatePlyStrain, rtPlatePlyReserve, rtPlateFlux, rtPlateGradient,
rtPlateReoDesign, rtPlateCreepStrain, rtPlateSoil, rtPlateUser,
rtPlateNodeReact or rtPlateNodeDisp.

ResultSubType
The result sub-type, one of stPlateLocal, stPlateGlobal, stPlateCombined,
stPlateSupport, stPlateDevLocal, stPlateDevGlobal, stPlateDevCombined or
the ID of a UCS in the model into which components the result is to be
resolved. Note the Global Cartesian coordinate system is defined as UCS 1.
Results are returned in a one-dimensional array PlateResult which consists of
contiguous blocks of data. Each block corresponds to a location on the plate. The
length NumColumns of each block depends on the requested result quantity and is
returned by St7GetPlateResultArray. The total number of these blocks NumPoints
depends on the input SampleLocation and is also returned. The total number of
quantities returned in PlateResult is therefore NumPoints*NumColumns.
Constants are provided that index specific result quantities within each block of data.
For example, the plate local xy force at the ith Gauss point is stored in the location:

PlateResult[(i-1)*NumColumns+ipPlateLocalxy]
These constants are specific to the result type requested – appropriate constants for
each result type are listed in the rest of this section.





Stress, Strain, Creep Strain, Moment, Curvature and Force results for stPlateLocal

- `ipPlateLocalxx` — Local xx component.
- `ipPlateLocalyy` — Local yy component.
- `ipPlateLocalzz` — Local zz component.
- `ipPlateLocalxy` — Local xy component.
- `ipPlateLocalyz` — Local yz component.
- `ipPlateLocalxz` — Local zx component.

Stress results for stPlateDevLocal

- `ipPlateLocalMean` — Mean.
- `ipPlateLocalDevxx` — Deviatoric xx component.
- `ipPlateLocalDevyy` — Deviatoric yy component.

Stress results for stPlateSupport

- `ipPlateEdgeSupport` — Edge support component.
- `ipPlateFaceSupport` — Face support component.

Stress, Strain, Creep Strain, Moment, Curvature and Force results for stPlateGlobal

- `ipPlateGlobalXX` — Global XX component.
- `ipPlateGlobalYY` — Global YY component.
- `ipPlateGlobalZZ` — Global ZZ component.
- `ipPlateGlobalXY` — Global XY component.
- `ipPlateGlobalYZ` — Global YZ component.
- `ipPlateGlobalZX` — Global ZX component.





Stress results for stPlateDevGlobal

- `ipPlateGlobalMean` — Mean.
- `ipPlateGlobalDevXX` — Deviatoric XX component.
- `ipPlateGlobalDevYY` — Deviatoric YY component.
- `ipPlateGlobalDevZZ` — Deviatoric ZZ component.

Stress, Strain, Creep Strain, Moment, Curvature and Force results for a UCS ID result
sub-type

- `ipPlateUCSXX` — UCS 11 component.
- `ipPlateUCSYY` — UCS 22 component.
- `ipPlateUCSZZ` — UCS 33 component.
- `ipPlateUCSXY` — UCS 12 component.
- `ipPlateUCSYZ` — UCS 23 component.
- `ipPlateUCSZX` — UCS 31 component.

Stress, Strain, Creep Strain, Moment, Curvature and Force results for
- `stPlateCombined`

- `ipPlateCombPrincipal11` — Principal 11 component.
- `ipPlateCombPrincipal22` — Principal 22 component.
- `ipPlateCombPrincipalAngle` — Principal axis angle.
- `ipPlateCombVonMises` — Von Mises quantity.
- `ipPlateCombTresca` — Tresca quantity.
- `ipPlateCombMohrCoulomb` — Mohr Coulomb quantity.
- `ipPlateCombDruckerPrager` — Drucker-Prager quantity.
- `ipPlateCombPlasticStrain` — Plastic strain.
- `ipPlateCombCreepEffRate` — Effective creep rate.





- `ipPlateCombCreepShrinkage` — Creep shrinkage.
- `ipPlateCombYieldIndex` — Yield index.

Stress results for stPlateDevCombined

- `ipPlateCombMean` — Mean.
- `ipPlateCombDev11` — Deviatoric principal 11 component.
- `ipPlateCombDev22` — Deviatoric principal 22 component.

Stress, Strain and Creep Strain results for stPlateGlobal (Axisymmetric)

- `ipPlateAxiGlobalRR` — Axisymmetric RR component.
- `ipPlateAxiGlobalZZ` — Axisymmetric ZZ component.
- `ipPlateAxiGlobalTT` — Axisymmetric TT component.
- `ipPlateAxiGlobalRZ` — Axisymmetric RZ component.

Stress, Strain and Creep Strain results for stPlateDevGlobal (Axisymmetric)

- `ipPlateAxiGlobalMean` — Mean.
- `ipPlateAxiGlobalDevRR` — Axisymmetric deviatoric RR component.
- `ipPlateAxiGlobalDevZZ` — Axisymmetric deviatoric ZZ component.
- `ipPlateAxiGlobalDevTT` — Axisymmetric deviatoric TT component.

Stress, Strain and Creep Strain results for stPlateCombined (Axisymmetric)

- `ipPlateAxiCombPrincipal11` — Axisymmetric principal 11 component.
- `ipPlateAxiCombPrincipal22` — Axisymmetric principal 22 component.
- `ipPlateAxiCombPrincipal33` — Axisymmetric principal 33 component.
- `ipPlateAxiCombVonMises` — Axisymmetric Von Mises quantity.





- `ipPlateAxiCombTresca` — Axisymmetric Tresca quantity.
- `ipPlateAxiCombMohrCoulomb` — Axisymmetric Mohr-Coulomb quantity.
- `ipPlateAxiCombDruckerPrager` — Axisymmetric Drucker-Prager quantity.
- `ipPlateAxiCombPlasticStrain` — Axisymmetric plastic strain quantity.
- `ipPlateAxiCombCreepEffRate` — Axisymmetric effective creep rate.
- `ipPlateAxiCombCreepShrinkage` — Axisymmetric creep shrinkage.
- `ipPlateAxiCombYieldIndex` — Axisymmetric yield index.

Stress results for stPlateDevCombined (Axisymmetric)

- `ipPlateAxiCombMean` — Mean.
- `ipPlateAxiCombDev11` — Axisymmetric deviatoric principal 11 component.
- `ipPlateAxiCombDev22` — Axisymmetric deviatoric principal 22 component.
- `ipPlateAxiCombDev33` — Axisymmetric deviatoric principal 33 component.

Ply Stress

- `ipPlyStress11` — Ply 11 stress component.
- `ipPlyStress22` — Ply 22 stress component.
- `ipPlyStress12` — Ply 12 stress component.
- `ipPlyILSx` — Interlamina Sx component.
- `ipPlyILSy` — Interlamina Sy component.

Ply Strain

- `ipPlyStrain11` — Ply 11 strain component.
- `ipPlyStrain22` — Ply 22 strain component.
- `ipPlyStrain12` — Ply 12 strain component.






Ply Reserve

- `ipPlyMaxStress` — Maximum stress.
- `ipPlyMaxStrain` — Maximum strain.
- `ipPlyTsaiHill` — Tsai-Hill measure.
- `ipPlyModTsaiWu` — Modified Tsai-Wu measure.
- `ipPlyHoffman` — Hoffman measure.
- `ipPlyInterlam` — Interlamina stress.

Soil

- `ipPlateSoilTotalPorePressure` — Total pore pressure.
- `ipPlateSoilExcessPorePressure` — Excess pore pressure.
- `ipPlateSoilOCRIndex` — OCR index.
- `ipPlateSoilStateIndex` — Failure index.
- `ipPlateSoilVoidRatio` — Void ratio.

Flux and Temperature Gradient results for stPlateLocal

- `ipPlateFluxLocalx` — Local x component.
- `ipPlateFluxLocaly` — Local y component.
- `ipPlateFluxLocalxy` — Local xy component.

Flux and Temeprature Gradient results for stPlateGlobal

- `ipPlateFluxGlobalX` — Global X component.
- `ipPlateFluxGlobalY` — Global Y component.
- `ipPlateFluxGlobalZ` — Global Z component.





- `ipPlateFluxGlobalXY` — Global XY component.
- `ipPlateFluxGlobalYZ` — Global YZ component.
- `ipPlateFluxGlobalZX` — Global ZX component.
- `ipPlateFluxGlobalSRSS` — Global SRSS component.

Flux and Temeprature Gradient results for a UCS ID result sub-type

- `ipPlateFluxUCSX` — UCS 1 component.
- `ipPlateFluxUCSY` — UCS 2 component.
- `ipPlateFluxUCSZ` — UCS 3 component.
- `ipPlateFluxUCSXY` — UCS 12 component.
- `ipPlateFluxUCSYZ` — UCS 23 component.
- `ipPlateFluxUCSZX` — UCS 31 component.
- `ipPlateFluxUCSSRSS` — UCS SRSS component.

Reinforcement Design

- `ipPlateRCWoodArmerMoment` — Wood-Armer moment.
- `ipPlateRCWoodArmerForce` — Wood-Armer force.
- `ipPlateRCSteelArea` — Steel area.
- `ipPlateRCSteelAreaLessBase` — Steel area less base area.
- `ipPlateRCSteelStress` — Steel stress.
- `ipPlateRCConcreteStrain` — Concrete strain ratio.
- `ipPlateRCBlockRatio` — Block ratio.

Node Reaction

- `ipPlateNodeReactFX` — FX component.





