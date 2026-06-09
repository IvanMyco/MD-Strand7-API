---
title: "Result Display Options"
source: "Strand7 R246 API Manual"
pages: 1107–1110
---

# Result Display Options

Entity Display Settings

- `ctBrickGlobalPressureX` — Contours of global pressure in the local x axis direction.
- `ctBrickGlobalPressureY` — Contours of global pressure in the local y axis direction.
- `ctBrickGlobalPressureZ` — Contours of global pressure in the local z axis direction.
- `ctBrickShearX` — Contours of face shear in the local x axis direction.
- `ctBrickShearY` — Contours of face shear in the local y axis direction.
- `ctBrickShearMagnitude` — Contours of face shear magnitude.
- `ctBrickNSMass` — Contours of non-structural mass.
- `ctBrickDynamicFactor` — Contours of non-structural mass dynamic factor.
- `ctBrickConvectionCoeff` — Contours of convection coefficient.
- `ctBrickConvectionAmbient` — Contours of convection ambient temperature.
- `ctBrickRaditionCoeff` — Contours of radiation coefficient.
- `ctBrickRadiationAmbient` — Contours of radiation ambient temperature.
- `ctBrickHeatFlux` — Contours of applied heat flux.
- `ctBrickHeatSource` — Contours of heat source.
- `ctBrickSoilStressSV` — Contours of soil stress SV.
- `ctBrickSoilStressKO` — Contours of soil stress KO.
- `ctBrickSoilStressSH` — Contours of soil stress SH.
- `ctBrickSoilRatioOCR` — Contours of soil ratio OCR.
- `ctBrickSoilRatioEO` — Contours of soil ratio EO.
- `ctBrickAgeAtFirstLoading` — Contours of age at first loading.





Element result contours can be displayed when viewing a model using the Strand7 API
model window with a result file open. These contours can be configured and generated
via the Integers array used in the St7SetBeamResultDisplay, St7SetPlateResultDisplay and
St7SetBrickResultDisplay functions.

Result Display Types

- `rtAsNone` — No result display.
- `rtAsContour` — Display result as element contour.
- `rtAsDiagram` — Display result as element diagram.
- `rtAsVector` — Display result as element vector.

Common Result Display Quantities

icDispC - Displacement results.
icVelC - Velocity results.
icAccC - Acceleration results.
icPhaseC - Phase results.
icReactC - Reaction results.
icTempC - Temperature results.
icNodeForceC - Element node force results.
icNodeFluxC - Flux results.

Beam Result Display Quantities

icBeamForceC - Beam force results.
icBeamStrainC - Beam strain results.
icBeamStressC - Beam stress results.






icBeamCreepStrainC - Beam creep strain results.
icBeamEnergyC - Beam energy results.
icBeamFluxC - Beam heat flux results.
icBeamTGradC - Beam temperature gradient results.

Plate Result Display Quantities

icPlateForceC - Plate force results.
icPlateMomentC - Plate moment results.
icPlateStressC - Plate stress results.
icPlateStrainC - Plate strain results.
icPlateCurvatureC - Plate curvature results.
icPlateCreepStrainC - Plate creep strain results.
icPlateEnergyC - Plate energy results.
icPlateFluxC - Plate heat flux results.
icPlateTGradC - Plate temperature gradient results.

Brick Result Display Quantities

icBrickStressC - Brick stress results.
icBrickStrainC - Brick strain results.
icBrickCreepStrainC - Brick creep strain results.
icBrickEnergyC - Brick energy results.
icBrickFluxC - Brick heat flux results.
icBrickTGradC - Brick temperature gradient results.





Result Display Axis

- `stBeamLocal` — use beam local axes.
- `stBeamPrincipal` — use beam principal axes.
- `stBeamGlobal` — use global axes.
- `stPlateLocal` — use plate local axes.
- `stPlateGlobal` — use plate global axes.
- `stPlateCombined` — show plate combined results.
- `stBrickLocal` — use brick local axes.
- `stBrickGlobal` — use brick global axes.
- `stBrickCombined` — show brick combined results.
OR the ID of a UCS in the model into which to resolve the result. Note the UCS IDs in a
model begin at an index of 2.

Result Display Components
This parameter is defined using an integer value and should be set according to the
Results Settings dialog available within Strand7. Indices start at 1 and increment
downwards and then to the right. For example, when displaying a contour of
displacement results for plates D(XYZ) the index is 10.

Diagram Result Display Components
The following diagram quantities are interpreted based on the result quantity selected as
in the Results Settings dialog. The results Integers array needs the following data defined.

- `ipDiagram1` — btTrue or btFalse.
- `ipDiagram2` — btTrue or btFalse.
- `ipDiagram3` — btTrue or btFalse.
- `ipDiagram4` — btTrue or btFalse.
- `ipDiagram5` — btTrue or btFalse.





