---
title: "Custom Results"
source: "Strand7 R246 API Manual"
pages: 1111–1118
---

# Custom Results

Result Display Options

- `ipDiagram6` — btTrue or btFalse.

Vector Result Display Components
The following vector quantities are interpreted based on the result quantity selected as in
the Results Settings dialog. The results Integers array needs the following data defined.
The results UCS is controlled using the St7SetWindowUCSCase function.

- `ipVector1` — btTrue or btFalse.
- `ipVector2` — btTrue or btFalse.
- `ipVector3` — btTrue or btFalse.
- `ipVector4` — btTrue or btFalse.
- `ipVector5` — btTrue or btFalse.
- `ipVector6` — btTrue or btFalse.





User defined results files can be created directly using the Strand7 API. Once created,
these results can be opened and manipulated in the same way as normal Strand7 result
files.
Custom results can be specified for the following basic quantities:

Node Results
rtNodeDisp, rtNodeVel, rtNodeAcc, rtNodeReact, rtNodeTemp or rtNodeFlux.
Beam Results
rtBeamForce, rtBeamStrain, rtBeamFlux or rtBeamNodeReact.
Plate Results
rtPlateStress, rtPlateStrain, rtPlateFlux or rtPlateNodeReact.
Brick Results
rtBrickStress, rtBrickStrain, rtBrickFlux or rtBrickNodeReact.

The following set of contants are available for indexing the Doubles array for the
appropriate functions of; St7SetResFileNodeResult, St7GetResFileNodeResult,
St7SetResFileBeamResult, St7GetResFileBeamResult, St7SetResFilePlateResult,
St7GetResFilePlateResult, St7SetResFileBrickResult or St7GetResFileBrickResult.

Nodal Displacement, Velocity, Acceleration and Reaction

- `ipNodeResFileDX` — Translational result in the X axis direction.
- `ipNodeResFileDY` — Translational result in the Y axis direction.
- `ipNodeResFileDZ` — Translational result in the Z axis direction.
- `ipNodeResFileRX` — Rotational result about the X axis.
- `ipNodeResFileRY` — Rotational result about the Y axis.
- `ipNodeResFileRZ` — Rotational result about the Z axis.
Note that nodal rotations are measured in degrees.





Nodal Temperature and Flux

- `ipNodeResTemp` — Temperature result.

Beam Force

- `ipBeamResFileSF1` — Shear force in the principal 1 axis direction.
- `ipBeamResFileSF2` — Shear force in the principal 2 axis direction.
- `ipBeamResFileAxial` — Axial force.
- `ipBeamResFileBM1` — Bending moment in the principal 1 axis direction.
- `ipBeamResFileBM2` — Bending moment in the principal 2 axis direction.
- `ipBeamResFileTorque` — Torque.
The above constants index contiguous blocks of results for each beam station, where
each block is kBeamResFileForceSize long. For example, the axial force at the ith
beam station is stored at:

Doubles[(i-1)*kBeamResFileForceSize+ipBeamResFileAxial].

Beam Strain

- `ipBeamResFileAxialStrain` — Axial strain.
- `ipBeamResFileCurvature1` — Curvature in the principal 1 axis direction.
- `ipBeamResFileCurvature2` — Curvature in the principal 2 axis direction.
- `ipBeamResFileTwist` — Twisting strain.
The above constants index contiguous blocks of results for each beam station, where
each block is kBeamResFileStrainSize long.

Beam Nodal Reaction

- `ipBeamResFileFX` — Force reaction in the X axis direction.





- `ipBeamResFileFY` — Force reaction in the Y axis direction.
- `ipBeamResFileFZ` — Force reaction in the Z axis direction.
- `ipBeamResFileMX` — Moment reaction in the X axis direction.
- `ipBeamResFileMY` — Moment reaction in the Y axis direction.
- `ipBeamResFileMZ` — Moment reaction in the Z axis direction.
The above constants index contiguous blocks of results for each beam end, where each
block is kBeamResFileReactSize long.

Beam Flux

- `ipBeamResFileF` — Beam heat flux.
- `ipBeamResFileG` — Beam temperature gradient.
The above constants index contiguous blocks of results for each beam end, where each
block is kBeamResFileFluxSize long.

Plate Stress
Plate stress results for linear analyses comprise the following eight constants only:

- `ipPlateShellResFileNxx` — Plate force in the local x axis direction.
- `ipPlateShellResFileNyy` — Plate force in the local y axis direction.
- `ipPlateShellResFileNxy` — Plate force in the local xy axis direction.
- `ipPlateShellResFileMxx` — Plate moment in the local x axis direction.
- `ipPlateShellResFileMyy` — Plate moment in the local y axis direction.
- `ipPlateShellResFileMxy` — Plate moment in the local xy axis direction.
- `ipPlateShellResFileQxz` — Plate shear force in the local xz axis direction.
- `ipPlateShellResFileQyz` — Plate shear force in the local yz axis direction.
Plate stress results for nonlinear analyses additionally comprise the following nine
constants:






- `ipPlateShellResFileZMinusSxx` — Plate stress in the local x axis direction, at the
minus Z plate surface.

- `ipPlateShellResFileZMinusSyy` — Plate stress in the local y axis direction, at the
minus Z plate surface.

- `ipPlateShellResFileZMinusSxy` — Plate stress in the local xy axis direction, at the
minus Z plate surface.

- `ipPlateShellResFileMidPlaneSxx` — Plate stress in the local x axis direction, at the
midplane plate surface.

- `ipPlateShellResFileMidPlaneSyy` — Plate stress in the local y axis direction, at the
midplane plate surface.

- `ipPlateShellResFileMidPlaneSxy` — Plate stress in the local xy axis direction, at the
midplane plate surface.

- `ipPlateShellResFileZPlusSxx` — Plate stress in the local x axis direction, at the plus
Z plate surface.

- `ipPlateShellResFileZPlusSyy` — Plate stress in the local y axis direction, at the plus
Z plate surface.

- `ipPlateShellResFileZPlusSxy` — Plate stress in the local xy axis direction, at the plus
Z plate surface.
The above constants index contiguous blocks of results for each plate Gauss point,
where each block is kPlateShellResFileStressSize long.

Plate Strain

- `ipPlateShellResFileExx` — Plate strain in the local x axis direction.
- `ipPlateShellResFileEyy` — Plate strain in the local y axis direction.
- `ipPlateShellResFileExy` — Plate strain in the local xy axis direction.
- `ipPlateShellResFileEzz` — Plate strain in the local z axis direction.
- `ipPlateShellResFileKxx` — Plate curvature in the local x axis direction.
- `ipPlateShellResFileKyy` — Plate curvature in the local y axis direction.
- `ipPlateShellResFileKxy` — Plate curvature in the local xy axis direction.





- `ipPlateShellResFileTxz` — Transverse plate strain in the local zx axis direction.
- `ipPlateShellResFileTyz` — Transverse plate strain in the local yz axis direction.
- `ipPlateShellResFileStoredE` — Stored elastic strain energy density.
- `ipPlateShellResFileSpentE` — Irreversible work performed, as an energy density.
The above constants index contiguous blocks of results for each plate Gauss point,
where each block is kPlateShellResFileStrainSize long.

2D Plate Stress

- `ipPlate2DResFileSXX` — Plate stress in the global X axis direction.
- `ipPlate2DResFileSYY` — Plate stress in the global Y axis direction.
- `ipPlate2DResFileSXY` — Plate stress in the global XY axis direction.
- `ipPlate2DResFileSZZ` — Plate stress in the global Z axis direction.
The above constants index contiguous blocks of results for each plate Gauss point,
where each block is kPlate2DResFileStressSize long.

2D Plate Strain

- `ipPlate2DResFileEXX` — Plate strain in the global X axis direction.
- `ipPlate2DResFileEYY` — Plate strain in the global Y axis direction.
- `ipPlate2DResFileEXY` — Plate strain in the global XY axis direction.
- `ipPlate2DResFileEZZ` — Plate strain in the global Z axis direction.
- `ipPlate2DResFileStoredE` — Stored elastic strain energy density.
- `ipPlate2DResFileSpentE` — Irreversible work performed, as an energy density.
The above constants index contiguous blocks of results for each plate Gauss point,
where each block is kPlate2DResFileStrainSize long.





Plate Nodal Reaction

- `ipPlateResFileFX` — Plate node reaction in the global X axis direction.
- `ipPlateResFileFY` — Plate node reaction in the global Y axis direction.
- `ipPlateResFileFZ` — Plate node reaction in the global Z axis direction.
- `ipPlateResFileMX` — Plate node reaction about the global X axis direction.
- `ipPlateResFileMY` — Plate node reaction about the global Y axis direction.
- `ipPlateResFileMZ` — Plate node reaction about the global Z axis direction.
The above constants index contiguous blocks of results for each plate node, where each
block is kPlateResFileReactSize long.

Plate Flux

- `ipPlateResFileFxx` — Plate heat flux in the local x axis direction.
- `ipPlateResFileFyy` — Plate heat flux in the local y axis direction.
- `ipPlateResFileGxx` — Plate temperature gradient in the local x axis direction.
- `ipPlateResFileGyy` — Plate temperature gradient in the local y axis direction.
The above constants index contiguous blocks of results for each plate Gauss point,
where each block is kPlateResFileFluxSize long.

Brick Stress

- `ipBrickResFileSXX` — Brick stress in the local x axis direction.
- `ipBrickResFileSYY` — Brick stress in the local y axis direction.
- `ipBrickResFileSZZ` — Brick stress in the local z axis direction.
- `ipBrickResFileSXY` — Brick stress in the local xy axis direction.
- `ipBrickResFileSYZ` — Brick stress in the local yz axis direction.
- `ipBrickResFileSZX` — Brick stress in the local zx axis direction.





The above constants index contiguous blocks of results for each brick Gauss point, where
each block is kBrickResFileStressSize long.

Brick Strain

- `ipBrickResFileExx` — Brick strain in the local x axis direction.
- `ipBrickResFileEyy` — Brick strain in the local y axis direction.
- `ipBrickResFileEzz` — Brick strain in the local z axis direction.
- `ipBrickResFileExy` — Brick strain in the local xy axis direction.
- `ipBrickResFileEyz` — Brick strain in the local yz axis direction.
- `ipBrickResFileEzx` — Brick strain in the local zx axis direction.
- `ipBrickResFileStoredE` — Stored elastic strain energy density.
- `ipBrickResFileSpentE` — Irreversible work performed, as an energy density.
The above constants index contiguous blocks of results for each brick Gauss point, where
each block is kBrickResFileStrainSize long.

Brick Nodal Reaction

- `ipBrickResFileFX` — Brick node reaction in the global X axis direction.
- `ipBrickResFileFY` — Brick node reaction in the global Y axis direction.
- `ipBrickResFileFZ` — Brick node reaction in the global Z axis direction.
The above constants index contiguous blocks of results for each brick node, where each
block is kBrickResFileReactSize long.

Brick Flux

- `ipBrickResFileFXX` — Brick heat flux in the local x axis direction.
- `ipBrickResFileFYY` — Brick heat flux in the local y axis direction.
- `ipBrickResFileFZZ` — Brick heat flux in the local z axis direction.





