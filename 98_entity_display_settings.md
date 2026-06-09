---
title: "Entity Display Settings"
source: "Strand7 R246 API Manual"
pages: 1095–1106
---

# Entity Display Settings

Creep Definitions
Generalised Graham Creep

[0..7] - Coefficients C1, C2, C3, C4, C5, C6, C7 and CT.

Generalised Blackburn Creep

[0..6] - Coefficients C1, C2, C3, C4, C5, C6 and C7.





There are a variety of display settings for each of the different entity types in Strand7.
These settings can be specified for each entity type via an Integer array parameter.
The following sets of constants are used when defining display options:

Node/Vertex Symbols
syDot1, syDot2, syDot3, syDot4, sySquare1, sySquare2, syDisk1, syDisk2, syCircle1, syCircle2,
syCircle3, sy3D1, sy3D2, sy3D3.

Filled Modes
fmPropertyColour, fmGroupColour, fmGlobalColour, fmPropertyWireframe,
fmGroupWireframe, fmOutlineWireframe, fmOrientation.

Number Modes
nmNone, nmByElement, nmByProperty, nmByPropertyName, nmByID.

Display Modes
dmLine, dmSection, dmSolid, dmSlice.

The Integer array can be specified for each entity type as follows:

Node

- `ipNodeSelectedColour` — Selected node colour as a 32 bit RGB value.
- `ipNodeUnselectedColour` — Unselected node colour as a 32 bit RGB value.
- `ipNodeShowFree` — Show free nodes, either btTrue or btFalse.
- `ipNodeNumberMode` — Numbering mode for node numbers, see Number Modes for
additional information.






- `ipNodeSymbol` — Symbol for node display, see Node/Vertex Symbols for additional
information.

Beam Element

- `ipBeamDisplay` — Beam display settings, see Display Modes for additional information.
- `ipBeamShowRefNode` — Show reference nodes, either btTrue or btFalse.
- `ipBeamShowOffset` — Show offsets, either btTrue or btFalse.
- `ipBeamMoveToOffset` — Move to offset, either btTrue or btFalse.
- `ipBeamLightShade` — Render with light shade, either btTrue or btFalse.
- `ipBeamGlobalColour` — Global beam colour as a 32 bit RGB colour.
- `ipBeamOutlineColour` — Outline colour as a 32 bit RGB colour.
- `ipBeamEnd1Colour` — End 1 colour as a 32 bit RGB colour.
- `ipBeamEnd2Colour` — End 2 colour as a 32 bit RGB colour.
- `ipBeamRefNodeColour` — Reference line colour as a 32 bit RGB colour.
- `ipBeamFilledMode` — Beam filled mode, one of dmLine, dmSection, dmSolid or dmSlice.
- `ipBeamContour` — Beam contour type, see Beam Contour Types for additional
information.

- `ipBeamShrink` — Shrink value as a percentage.
- `ipBeamRoundFacets` — Number of facets used to render round beams.
- `ipBeamSpringCoils` — Number of coils used to display springs.
- `ipBeamSpringAspect` — Aspect ratio for spring elements.
- `ipBeamThickness` — Line thickness.
- `ipBeamSections` — Number of length-wise sections.
- `ipBeamOutlines` — Show outlines, either omOutlineOn or omOutlineOff.
- `ipBeamShowAxes` — Show element axes, either btTrue or btFalse.





- `ipBeamNumberMode` — Numbering mode for beam numbers, see Number Modes for
additional information.

Plate Element

- `ipPlateDisplay` — Plate display settings, see Display Modes for additional information.
- `ipPlateLightShade` — Render with light shade, either btTrue or btFalse.
- `ipPlateGlobalColour` — Global plate colour as a 32 bit RGB colour.
- `ipPlateOutlineColour` — Outline colour as a 32 bit RGB colour.
- `ipPlateZPlusColour` — Z-plus orientation colour as a 32 bit RGB value.
- `ipPlateZMinusColour` — Z-minus orientation colour as a 32 bit RGB colour.
- `ipPlateOffsetColour` — Offset line colour as a 32 bit RGB value.
- `ipPlateFilledMode` — Plate filled mode, see Filled Modes for additional information.
- `ipPlateContour` — Plate contour type, see Plate Contour Types for additional
information.

- `ipPlateShrink` — Shrink value as a percentage.
- `ipPlateOutlines` — Show plate outlines, one of omOutlineOn, omOutlineOff or
omOutlineFacet.

- `ipPlateOutlineThickness` — Plate outline line thickness.
- `ipPlateShowAxes` — Show plate axes, either btTrue or btFalse.
- `ipPlateAxisOnPly` — Ply number for axes display.
- `ipPlateOffset` — Show plate offsets, either btTrue or btFalse.
- `ipPlateMoveToOffset` — Move to offsets, either btTrue or btFalse.
- `ipPlateNumberMode` — Plate numbering modes, see Number Modes for additional
information.

Brick Element

- `ipBrickLightShade` — Render with light shade, either btTrue or btFalse.





- `ipBrickGlobalColour` — Brick global colour as a 32 bit RGB value.
- `ipBrickOutlineColour` — Outline colour as a 32 bit RGB value.
- `ipBrickFilledMode` — Brick filled mode, see Filled Modes for additional information.
- `ipBrickContour` — Brick contour type, see Brick Contour Types for additional
information.

- `ipBrickShrink` — Shrink value as a percentage.
- `ipBrickOutlines` — Show outlines, one of omOutlineOn, omOutlineOff or
omOutlineFacet.

- `ipBrickOutlineThickness` — Brick outline thickness.
- `ipBrickShowFreeFaces` — Show brick free faces, either btTrue or btFalse.
- `ipBrickAxes1` — Show brick 1-axis, either btTrue or btFalse.
- `ipBrickAxes2` — Show brick 2-axis, either btTrue or btFalse.
- `ipBrickAxes3` — Show brick 3-axis, either btTrue or btFalse.
- `ipBrickNumberMode` — Brick number mode, see Number Modes for additional
information.

- `ipBrickShowAllFaces` — Show all brick faces, either btTrue or btFalse.

Link

- `ipLinkGlobalColour` — Link global colour as a 32 bit RGB value.
- `ipLinkMasterSlaveColour` — Master-Slave link colour as a 32 bit RGB value.
- `ipLinkSectorSymmColour` — Sector-symmetry link colour as a 32 bit RGB value.
- `ipLinkCouplingColour` — Coupling link colour as a 32 bit RGB value.
- `ipLinkPinnedColour` — Pinned link colour as a 32 bit RGB value.
- `ipLinkRigidColour` — Rigid link colour as a 32 bit RGB value.
- `ipLinkShrinkColour` — Shrink link colour as a 32 bit RGB value.
- `ipLinkTwoPointColour` — Two-Point link colour as a 32 bit RGB value.





- `ipLinkAttachmentColour` — Attachment link colour as a 32 bit RGB value.
- `ipLinkMultiPointColour` — Multi-Point link colour as a 32 bit RGB value.
- `ipLinkFilledMode` — Link filled mode, see Filled Modes for additional information.
- `ipLinkNumberMode` — Link numbering mode, see Number Modes for additional
information.

Load Path

- `ipLoadPathColour` — Load path colour as a 32 bit RGB value.
- `ipLoadPathColourMode` — Load path colour mode, one of
cmLoadPathTemplateColour, cmLoadPathGroupColour, cmLoadPathColour or
cmLoadPathGlobalColour.

- `ipLoadPathNumberMode` — Load path numbering mode, see Number Modes for
additional information.

- `ipLoadPathShowDivisions` — Show path divisions, either btTrue or btFalse.
- `ipLoadPathThickness` — Load path thickness.

Vertex

- `ipVertexFreeColour` — Free vertex colour as a 32 bit RGB value.
- `ipVertexFixedColour` — Fixed vertex colour as a 32 bit RGB value.
- `ipVertexSelectedColour` — Selected vertex colour as a 32 bit RGB colour.
- `ipVertextNumberMode` — Vertex numbering mode, see Number Modes for additional
information.

- `ipVertexSymbol` — Vertex symbol, see Node/Vertex Symbols for additional information.

Geometry Edge

- `ipEdgeShow` — Show edges, either btTrue or btFalse.
- `ipEdgeShowNonInterp` — Show non-interpolated edges, either btTrue or btFalse.






- `ipEdgeStyle` — Edge style, either esThinEdge or esThickEdge.
- `ipEdgeColourMode` — Edge colour mode.
- `ipEdgeColour` — Edge colour as a 32 bit RGB value.
- `ipEdgeNonInterpColour` — Non-Interpolated edge colour as a 32 bit RGB value.

Geometry Face

- `ipFaceWireframeColour` — Wireframe colour as a 32 bit RGB value.
- `ipFaceShowWireframes` — Show wireframes, either btTrue or btFalse.
- `ipFaceShowControlPoints` — Show control points, either btTrue or btFalse.
- `ipFaceShowNormals` — Show face normals, either btTrue or btFalse.
- `ipFaceWireframeStyle` — Wireframe style, either wsDepthShaded or
wsConstantColour.

- `ipFaceWireframeColourMode` — Wireframe colour mode.
- `ipFaceWireframeDensity` — Wireframe density.

The following pre-processor contour types can be specified for each entity type:

Beam Contour Types

- `ctBeamNone` — No contour.
- `ctBeamLength` — Contours of beam length.
- `ctBeamAxis1` — Contours of local axis 1 component.
- `ctBeamAxis2` — Contours of local axis 2 component.
- `ctBeamAxis3` — Contours of local axis 3 component.
- `ctBeamEA` — Contours of EA product.
- `ctBeamEI11` — Contours of EI11 product.





- `ctBeamEI22` — Contours of EI22 product.
- `ctBeamGJ` — Contours of GJ product.
- `ctBeamEAFactor` — Contours of EA factor.
- `ctBeamEI11Factor` — Contours of EI11 factor.
- `ctBeamEI22Factor` — Contours of EI22 factor.
- `ctBeamGJFactor` — Contours of GJ factor.
- `ctBeamOffset1` — Contours of offset in the local 1 axis direction.
- `ctBeamOffset2` — Contours of offset in the local 2 axis direction.
- `ctBeamStiffnessFactor1` — Contours of stiffness factor 1.
- `ctBeamStiffnessFactor2` — Contours of stiffness factor 2.
- `ctBeamStiffnessFactor3` — Contours of stiffness factor 3.
- `ctBeamStiffnessFactor4` — Contours of stiffness factor 4.
- `ctBeamStiffnessFactor5` — Contours of stiffness factor 5.
- `ctBeamStiffnessFactor6` — Contours of stiffness factor 6.
- `ctBeamMassFactor` — Contours of mass factor.
- `ctBeamSupport1` — Contours of support in the local 1 axis direction.
- `ctBeamSupport2` — Contours of support in the local 2 axis direction.
- `ctBeamTemperature` — Contours of applied temperature.
- `ctBeamPreTension` — Contours of pre-tension.
- `ctBeamPreStrain` — Contours of pre-strain.
- `ctBeamTempGradient1` — Contours of applied temperature gradient in the local 1 axis
direction.

- `ctBeamTempGradient2` — Contours of applied temperature gradient in the local 2 axis
direction.

- `ctBeamPipePressureIn` — Contours of internal pipe pressure.
- `ctBeamPipePressureOut` — Contours of external pipe pressure.





- `ctBeamPipeTempIn` — Contours of internal pipe temperature.
- `ctBeamPipeTempOut` — Contours of external pipe temperature.
- `ctBeamConvectionCoeff` — Contours of convection coefficient.
- `ctBeamConvectionAmbient` — Contours of ambient convection temperature.
- `ctBeamRadiationCoeff` — Contours of radiation coefficient.
- `ctBeamRadiationAmbient` — Contours of ambient radiation temperature.
- `ctBeamHeatFlux` — Contours of applied beam heat flux.
- `ctBeamHeatSource` — Contours of heat source.
- `ctBeamAgeAtFirstLoading` — Contours of age at first loading.

Plate Contour Types

- `ctPlateNone` — No Contour.
- `ctPlateAspectRatioMin` — Contours of minimum aspect ratio.
- `ctPlateAspectRatioMax` — Contours of maximum aspect ratio.
- `ctPlateWarping` — Contours of warping.
- `ctPlateInternalAngle` — Contours of internal angle.
- `ctPlateInternalAngleRatio` — Contours of internal angle ratio.
- `ctPlateDiscreteThicknessM` — Contours of discrete membrane thickness.
- `ctPlateContinuousThicknessM` — Contours of continuous membrane thickness.
- `ctPlateDiscreteThicknessB` — Contours of discrete bending thickness.
- `ctPlateContinuousThicknessB` — Contours of continuous bending thickness.
- `ctPlateOffset` — Contours of normal offset.
- `ctPlateArea` — Contours of area.
- `ctPlateAxis1` — Contours of axis 1 component.
- `ctPlateAxis2` — Contours of axis 2 component.




- `ctPlateAxis3` — Contours of axis 3 component.
- `ctPlateTemperature` — Contours of applied temperature.
- `ctPlateEdgeSupport` — Contours of edge support.
- `ctPlateFaceSupport` — Contours of face support.
- `ctPlatePreStressX` — Contours of applied pre-stress in the local x axis direction.
- `ctPlatePreStressY` — Contours of applied pre-stress in the local y axis direction.
- `ctPlatePresStressZ` — Contours of applied pre-stress in the local z axis direction.
- `ctPlatePreStressMagnitude` — Contours of applied pre-stress magnitude.
- `ctPlatePreStrainX` — Contours of applied pre-strain in the local x axis direction.
- `ctPlatePreStrainY` — Contours of applied pre-strain in the local y axis direction.
- `ctPlatePreStrainZ` — Contours of applied pre-strain in the local z axis direction.
- `ctPlatePreStrainMagnitude` — Contours of applied pre-strain magnitude.
- `ctPlateTempGradient` — Contours of applied temperature gradient.
- `ctPlateEdgePressure` — Contours of applied edge pressure.
- `ctPlateEdgeShear` — Contours of applied edge shear.
- `ctPlateEdgeNormalShear` — Contours of applied edge normal shear.
- `ctPlatePressureNormal` — Contours of applied normal pressure.
- `ctPlatePressureGlobal` — Contours of applied global pressure.
- `ctPlatePressureGlobalX` — Contours of applied pressure in the global X axis
direction.

- `ctPlatePressureGlobalY` — Contours of applied pressure in the global Y axis
direction.

- `ctPlatePressureGlobalZ` — Contours of applied pressure in the global Z axis direction.
- `ctPlateFaceShearX` — Contours of applied face shear in the local x axis direction.
- `ctPlateFaceShearY` — Contours of applied face shear in the local y axis direction.
- `ctPlateFaceShearMagnitude` — Contours of applied face shear magnitude.





- `ctPlateNSMass` — Contours of non-structural mass.
- `ctPlateDynamicFactor` — Contours of non-structural mass dynamic factor.
- `ctPlateConvectionCoeff` — Contours of convection coefficient.
- `ctPlateConvectionAmbient` — Contours of convection ambient temperature.
- `ctPlateRadiationCoeff` — Contours of radiation coefficient.
- `ctPlateRadiationAmbient` — Contours of radiation ambient temperature.
- `ctPlateHeatFlux` — Contours of applied heat flux.
- `ctPlateConvectionCoeffZPlus` — Contours of upper face convection coefficient.
- `ctPlateConvectionCoeffZMinus` — Contours of lower face convection coefficient.
- `ctPlateConvectionAmbientZPlus` — Contours of upper face convection ambient
temperature.

- `ctPlateConvectionAmbientZMinus` — Contours of lower face convection ambient
temperature.

- `ctPlateRadiationCoeffZPlus` — Contours of upper face radiation coefficient.
- `ctPlateRadiationCoeffZMinus` — Contours of lower face radiation coefficient.
- `ctPlateRadiationAmbientZPlus` — Contours of upper face radiation ambient
temperature.

- `ctPlateRadiationAmbientZMinus` — Contours of lower face radiation ambient
temperature.

- `ctPlateHeatSource` — Contours of applied heat source.
- `ctPlateSoilStressSV` — Contours of applied soil stress SV.
- `ctPlateSoilStressKO` — Contours of applied soil stress KO.
- `ctPlateSoilStressSH` — Contours of applied soil stress SH.
- `ctPlateSoilRatioOCR` — Contours of applied soil ratio OCR.
- `ctPlateSoilRatioEO` — Contours of applied soil ratio EO.
- `ctPlateAgeAtFirstLoading` — Contours of applied age at first loading.





Brick Contour Types

- `ctBrickNone` — No contour.
- `ctBrickAspectRatioMin` — Contours of minimum aspect ratio.
- `ctBrickAspectRatioMax` — Contours of maximum aspect ratio.
- `ctBrickVolume` — Contours of brick volume.
- `ctBrickDeterminant` — Contours of determinant.
- `ctBrickInternalAngle` — Contours of internal angle.
- `ctBrickMixedProduct` — Contours of mixed product.
- `ctBrickDihedral` — Contours of dihedral.
- `ctBrickAxis1` — Contours of axis 1 component.
- `ctBrickAxis2` — Contours of axis 2 component.
- `ctBrickAxis3` — Contours of axis 3 component.
- `ctBrickTemperature` — Contours of applied temperature.
- `ctBrickSupport` — Contours of face support.
- `ctBrickPreStressX` — Contours of pre-stress in the local x axis direction.
- `ctBrickPreStressY` — Contours of pre-stress in the local y axis direction.
- `ctBrickPreStressZ` — Contours of pre-stress in the local x axis direction.
- `ctBrickPreStressMagnitude` — Contours of pre-stress magnitude.
- `ctBrickPreStrainX` — Contours of pre-strain in the local x axis direction.
- `ctBrickPreStrainY` — Contours of pre-stress in the local y axis direction.
- `ctBrickPreStrainZ` — Contours of pre-stress in the local z axis direction.
- `ctBrickPreStrainMagnitude` — Contours of pre-strain magnitude.
- `ctBrickNormalPressure` — Contours of applied normal pressure.
- `ctBrickGlobalPressure` — Contours of applied global pressure.




