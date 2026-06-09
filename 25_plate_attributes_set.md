---
title: "Plate Attributes – Set"
source: "Strand7 R246 API Manual"
pages: 306–339
---

# Plate Attributes – Set

ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen


---

### `St7SetPlateID`

Sets the ID number for the specified plate.

**Syntax**

```c
long St7SetPlateID(long uID, long PlateNum, long PlateID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — The plate number.
- `PlateID` — The plate ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SetPlateXAngle1`

Sets the local axis angle for the specified plate. This angle controls the rotation of
the plate local XY axes about the local Z axis.

**Syntax**

```c
long St7SetPlateXAngle1(long uID, long PlateNum, double*
Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — The plate number.
- `Doubles[0]` — The angle describing the rotation of the plate local axis system about the local Z axis. See Plate Local Coordinates for further information.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetPlateThickness2`

Sets the thickness attribute of the specified plate element, overriding the plate
property thickness – see St7SetPlateThickness to set the plate property thickness.

**Syntax**

```c
long St7SetPlateThickness2(long uID, long PlateNum, double*
Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — The plate number.
- `Doubles[0..1]` — [0] - The membrane thickness of the plate. [1] - The bending thickness of the plate.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,


ERR7_InvalidLoadCase, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetPlateOffset1`

Sets the offset for the specified plate element. The offset is applied according to
the plate local Z axis direction and is uniform over the element surface.

**Syntax**

```c
long St7SetPlateOffset1(long uID, long PlateNum, double*
Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `Doubles[0]` — Plate offset in the local Z axis direction.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetPlateEdgeSupport1F`

Sets the elastic edge support value for the specified plate. The support acts
normal to the specified plate edge and is uniform along the edge length.

**Syntax**

```c
long St7SetPlateEdgeSupport1F(long uID, long PlateNum, long
CaseNum, long EdgeNum, long Status, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `CaseNum` — Freedom case number.
- `EdgeNum` — Edge identifier, one of 1, 2, 3 or 4.
- `Status` — Compression-only flag, either btTrue or btFalse.
- `Doubles[0]` — Elastic support value for the specified plate edge.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidPlateEdge,
ERR7_InvalidUCSID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SetPlateFaceSupport1F`

Sets the elastic face support value for the specified plate. The support acts
according to the plate local Z axis direction and is constant over the element
surface.

**Syntax**

```c
long St7SetPlateFaceSupport1F(long uID, long PlateNum, long
CaseNum, long Status, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `CaseNum` — Freedom case number.
- `Status` — Compression-only flag, either btTrue or btFalse.
- `Doubles[0]` — Elastic support value for the specified plate.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetPlateEdgeRelease1`

Sets the edge release conditions for the specified plate.

**Syntax**

```c
long St7SetPlateEdgeRelease1(long uID, long PlateNum, long
EdgeNum, long* Status)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `EdgeNum` — Edge identifier, one of 1, 2, 3 or 4.

**Output Parameters**

- `Status[0]` — Release flag, either btTrue or btFalse.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidPlateEdge,
ERR7_InvalidUCSID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SetPlatePreLoad3`

Sets the pre-load conditions for the specified plate.

**Syntax**

```c
long St7SetPlatePreLoad3(long uID, long PlateNum, long
CaseNum, long LoadType, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `CaseNum` — Load case number.
- `LoadType` — Pre-load type, either plPlatePreStrain or plPlatePreStress.
- `Doubles[0..2]` — A 3 element array describing the pre-load condition. Doubles[i-1] describes the pre-load in the ith local axis direction.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidPreLoadType,
ERR7_InvalidUCSID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SetPlateTempGradient1`

Sets the temperature gradient for the specified plate. The temperature gradient
acts according to the plate local Z axis direction and is constant over the
element surface. This attribute is only active for static and dynamic structural
analysis.

**Syntax**

```c
long St7SetPlateTempGradient1(long uID, long PlateNum, long
CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `CaseNum` — Load case number.
- `Doubles[0]` — Temperature gradient in the local Z axis direction.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetPlatePointForce6`

Assigns a point force to the specified plate.

**Syntax**

```c
long St7SetPlatePointForce6(long uID, long PlateNum, long
CaseNum, long Position, long ID, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `CaseNum` — Load case number.
- `Position` — Position identifier, either axUCS or axLocal.
- `ID` — Local ID number for the point force.
- `Doubles[0..5]` — [0..2] - Components of applied force in the Global Cartesian coordinate system. axUCS: [3..5] - XYZ position of point force in the Global Cartesian coordinate system. axLocal: [3..4] - UV position of point force in the local element coordinate system.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_InvalidPositionType,
ERR7_InvalidUCSID, ERR7_InvalidUVPos, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetPlatePointMoment6`

Assigns a point moment to the specified plate.

**Syntax**

```c
long St7SetPlatePointMoment6(long uID, long PlateNum, long
CaseNum, long Position, long ID, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `CaseNum` — Load case number.
- `Position` — Position identifier, either axUCS or axLocal.
- `ID` — Local ID number for the point moment.
- `Doubles[0..5]` — [0..2] - Components of applied moment in the Global Cartesian coordinate system. axUCS: [3..5] - XYZ position of point moment in the Global Cartesian coordinate system. axLocal: [3..4] - UV position of point moment in the local element coordinate system.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,


ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_InvalidPositionType,
ERR7_InvalidUCSID, ERR7_InvalidUVPos, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetPlateEdgePressure1`

Assigns a pressure to the specified plate edge. The pressure is applied in the
plane of the element, perpendicular to the plate edge.

**Syntax**

```c
long St7SetPlateEdgePressure1(long uID, long PlateNum, long
CaseNum, long EdgeNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `CaseNum` — Load case number.
- `EdgeNum` — Edge identifier, one of 1, 2, 3 or 4.
- `Doubles[0]` — Edge pressure for the specified plate edge, with positive pressures directed away from the plate.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidPlateEdge,
ERR7_InvalidUCSID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SetPlateEdgeShear1`

Assigns a shear stress to the specified plate edge. The shear stress is applied
tangential to the plate edge.

**Syntax**

```c
long St7SetPlateEdgeShear1(long uID, long PlateNum, long
CaseNum, long EdgeNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `CaseNum` — Load case number.
- `EdgeNum` — Edge identifier, one of 1, 2, 3 or 4.
- `Doubles[0]` — Edge shear stress.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidPlateEdge,
ERR7_InvalidUCSID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SetPlateEdgeNormalShear1`

Assigns a normal shear stress to the specified plate edge. The shear stress acts
normal to the plate surface at its edge, in the local +Z direction.

**Syntax**

```c
long St7SetPlateEdgeNormalShear1(long uID, long PlateNum,
long CaseNum, long EdgeNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `CaseNum` — Load case number.
- `EdgeNum` — Edge identifier, one of 1, 2, 3 or 4.
- `Doubles[0]` — Edge normal shear stress.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidPlateEdge,
ERR7_InvalidUCSID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SetPlateNormalPressure1`

Assigns a face pressure to the specified plate. The pressure is applied according
to the plate local Z axis direction.

**Syntax**

```c
long St7SetPlateNormalPressure1(long uID, long PlateNum,
long CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `CaseNum` — Load case number.
- `Doubles[0]` — Normal face pressure for the specified plate. Positive pressures are directed in the local Z axis direction.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetPlateGlobalPressure3`

Assigns a face pressure to the specified plate. The pressure is applied according
to the XYZ components specified.

**Syntax**

```c
long St7SetPlateGlobalPressure3(long uID, long PlateNum,
long ProjectFlag, long CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `ProjectFlag` — btTrue or btFalse.
- `CaseNum` — Load case number.
- `Doubles[0..2]` — A 3 element array describing the XYZ components of the applied pressure in the Global Cartesian Coordinate system.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetPlateShear2`

Assigns a face shear stress to the specified plate. The shear stress is applied in the
plane of the element.

**Syntax**

```c
long St7SetPlateShear2(long uID, long PlateNum, long
CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `CaseNum` — Load case number.
- `Doubles[0..1]` — A 2 element array that describes the applied shear stress according to the local plate XY axis system.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,


ERR7_InvalidLoadCase, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetPlateNSMass5`

Sets the non-structural mass properties for the specified plate.

**Syntax**

```c
long St7SetPlateNSMass5(long uID, long PlateNum, long
CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `CaseNum` — Load case number.
- `Doubles[0..5]` — [0] - Non-structural mass for the specified plate. [1] - Dynamic factor for the specified plate. This factor is used to scale the non-structural mass when performing dynamic analyses. [2..5] - A 3 element array describing the offset in the XYZ Global Cartesian coordinate system.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetPlateEdgeConvection2`

Sets the thermal convection coefficient and ambient temperature for the
specified plate edge. This attribute is only used when performing heat transfer
analysis.

**Syntax**

```c
long St7SetPlateEdgeConvection2(long uID, long PlateNum,
long CaseNum, long EdgeNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `CaseNum` — Load case number.
- `EdgeNum` — Local edge number, one of 1, 2, 3 or 4.
- `Doubles[0..1]` — [0] - Edge convection coefficient. [1] - Ambient temperature.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_InvalidPlateEdge,
ERR7_InvalidUCSID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SetPlateEdgeConvectionTables`

Specifies the tables associated with edge convection properties for the specified
plate edge. A Factor vs Temperature table may apply to the convection
coefficient and Factor vs Time tables may apply to both the convection
coefficient and ambient temperature.

**Syntax**

```c
long St7SetPlateEdgeConvectionTables(long uID, long
PlateNum, long CaseNum, long EdgeNum, long* Tables)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `CaseNum` — Load case number.
- `EdgeNum` — Local edge number, one of 1, 2, 3 or 4.
- `Tables[0..2]` — [0] - Factor vs Time table ID associated with the ambient temperature, use zero for none. [1] - Factor vs Temperature table ID associated with the edge convection coefficient, use zero for none. [2] - Factor vs Time table ID associated with the edge convection coefficient, use zero for none.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_InvalidTableType,


ERR7_InvalidPlateEdge, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_TableDoesNotExist
```


---

### `St7SetPlateEdgeRadiation2`

Sets the thermal radiation coefficient and ambient temperature for the specified
plate edge.

**Syntax**

```c
long St7SetPlateEdgeRadiation2(long uID, long PlateNum,
long CaseNum, long EdgeNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `CaseNum` — Load case number.
- `EdgeNum` — Local edge number, one of 1, 2, 3 or 4.
- `Doubles[0..1]` — [0] - Radiation coefficient. [1] - Ambient temperature.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_InvalidPlateEdge,
ERR7_InvalidUCSID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SetPlateEdgeRadiationTables`

Specifies the tables associated with the edge thermal radiation properties of a
specified plate edge. A Factor vs Temperature table may apply to the radiation
coefficient and Factor vs Time tables may apply to both the radiation coefficient
and ambient temperature.

**Syntax**

```c
long St7SetPlateEdgeRadiationTables(long uID, long PlateNum,
long CaseNum, long EdgeNum, long* Tables)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `CaseNum` — Load case number.
- `EdgeNum` — Local edge number, one of 1, 2, 3 or 4.
- `Tables[0..2]` — [0] - Table ID number for the Factor vs Time table associated with the radiation coefficient. [1] - Table ID number for the Factor vs Temperature table associated with the radiation coefficient. [2] - Table ID number for the Factor vs Time table associated with the ambient temperature.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_InvalidPlateEdge,


ERR7_InvalidTableType, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_TableDoesNotExist
```


---

### `St7SetPlateFlux1`

Sets the heat flux for the specified plate edge.

**Syntax**

```c
long St7SetPlateFlux1(long uID, long PlateNum, long CaseNum,
long EdgeNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `CaseNum` — Load case number.
- `EdgeNum` — Local edge number, one of 1, 2, 3 or 4.
- `Doubles[0]` — The heat flux through the plate edge.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_InvalidPlateEdge,
ERR7_InvalidUCSID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SetPlateFluxTables`

Specified the tables to be associated with the heat flux for the specified plate
edge. Both a Factor vs Time and a Factor vs Temperature table may be assigned.

**Syntax**

```c
long St7SetPlateFluxTables(long uID, long PlateNum, long
CaseNum, long EdgeNum, long* Tables)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `CaseNum` — Load case number.
- `EdgeNum` — Local edge number, one of 1, 2, 3 or 4.
- `Tables[0..1]` — [0] - Factor vs Time table ID associated with the edge heat flux, use zero for none. [1] - Factor vs Temperature table ID associated with the edge heat flux, use zero for none.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_InvalidPlateEdge,
ERR7_InvalidTableType, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_TableDoesNotExist
```


---

### `St7SetPlateFaceConvection2`

Sets the thermal convection coefficient and ambient temperature for the
specified plate face. This attribute is only used when performing heat transfer
analysis.

**Syntax**

```c
long St7SetPlateFaceConvection2(long uID, long PlateNum,
long CaseNum, long Surface, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `CaseNum` — Load case number.
- `Surface` — Local plate surface, either psPlateZMinus or psPlateZPlus.
- `Doubles[0..1]` — [0] - Convection coefficient. [1] - Ambient temperature.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_InvalidPlateSurface,
ERR7_InvalidUCSID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SetPlateFaceConvectionTables`

Specifies the tables associated with thermal convection properties for the
specified plate face. A Factor vs Temperature table may apply to the
convection coefficient and Factor vs Time tables may apply to both the
convection coefficient and ambient temperature.

**Syntax**

```c
long St7SetPlateFaceConvectionTables(long uID, long
PlateNum, long CaseNum, long Surface, long* Tables)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `CaseNum` — Load case number.
- `Surface` — Local plate surface number, either psPlateZMinus or psPlateZPlus.
- `Tables[0..2]` — [0] - Factor vs Time table ID associated with the ambient temperature, use zero for none. [1] - Factor vs Temperature table ID associated with the convection coefficient, use zero for none. [2] - Factor vs Time table ID associated with the convection coefficient, use zero for none.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_InvalidPlateSurface,


ERR7_InvalidTableType, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_TableDoesNotExist
```


---

### `St7SetPlateFaceRadiation2`

Sets the thermal radiation coefficient and ambient temperature for the specified
plate face.

**Syntax**

```c
long St7SetPlateFaceRadiation2(long uID, long PlateNum,
long CaseNum, long Surface, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `CaseNum` — Load case number.
- `Surface` — Local plate face, either psPlateZMinus or psPlateZPlus.
- `Doubles[0..1]` — [0] - Radiation coefficient. [1] - Ambient temperature.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_InvalidPlateSurface,
ERR7_InvalidUCSID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SetPlateFaceRadiationTables`

Specifies the tables to be associated with the radiation properties of a specified
plate face. A Factor vs Temperature table may apply to the radiation coefficient
and Factor vs Time tables may apply to both the radiation coefficient and
ambient temperature.

**Syntax**

```c
long St7SetPlateFaceRadiationTables(long uID, long PlateNum,
long CaseNum, long Surface, long* Tables)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `CaseNum` — Load case number.
- `Surface` — Local plate surface, either psPlateZMinus or psPlateZPlus.
- `Tables[0..2]` — [0] - Factor vs Time table ID associated with the ambient temperature, use zero for none. [1] - Factor vs Temperature table ID associated with the radiation coefficient, use zero for none. [2] - Factor vs Time table ID associated with the radiation coefficient, use zero for none.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_InvalidPlateSurface,


ERR7_InvalidTableType, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_TableDoesNotExist
```


---

### `St7SetPlateHeatSource1`

Sets the thermal heat source for the specified plate.

**Syntax**

```c
long St7SetPlateHeatSource1(long uID, long PlateNum, long
CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `CaseNum` — Load case number.
- `Doubles[0]` — Thermal heat source value.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetPlateHeatSourceTables`

Specifies the tables to be associated with the thermal heat source for the
specified plate. Both a Factor vs Time and Factor vs Temperature table may be
assigned.

**Syntax**

```c
long St7SetPlateHeatSourceTables(long uID, long PlateNum,
long CaseNum, long* Tables)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `CaseNum` — Load case number.
- `Tables[0..1]` — [0] - Factor vs Time table ID associated with the heat source, use zero for none. [1] - Factor vs Temperature table ID associated with the heat source, use zero for none.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_InvalidTableType,
ERR7_InvalidUCSID, ERR7_NoError, ERR7_ResultFileIsOpen,
ERR7_TableDoesNotExist
```


---

### `St7SetPlateSoilStress2`

Sets the in-situ soil stress for the specified plate. This attribute is only active for
plates of property type soil.

**Syntax**

```c
long St7SetPlateSoilStress2(long uID, long PlateNum, long
CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `CaseNum` — Load case number.
- `Doubles[0..1]` — A 2 element array containing the initial vertical stress and the horizontal stress ratio.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetPlateSoilRatio2`

Sets the in-situ soil ratios for the specified plate. This attribute is only active for
plates of property type soil.

**Syntax**

```c
long St7SetPlateSoilRatio2(long uID, long PlateNum, long
CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `CaseNum` — Load case number.
- `Doubles[0..1]` — A 2 element array containing the overconsolidation ratio and the initial void ratio.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetPlateResponse`

Assigns a response variable to the specified plate. Response variables are only
used by the Load Influence solver.

**Syntax**

```c
long St7SetPlateResponse(long uID, long PlateNum, long
CaseNum, long ResponseType, long UCSId, long* Status)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `CaseNum` — Load case number.
- `ResponseType` — Response variable type, either rePlateForce or rePlateMoment.
- `UCSId` — UCS ID number.
- `Status[0..5]` — A 6 element array describing which force/moment components are flagged as response variables according to the 123 axis convention in the specified UCS - [11, 22, 33, 12, 23, 31].

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidBeamEnd,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidLoadCase, ERR7_InvalidResponseType,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SetPlateLoadPatch4`

Sets the load patch type for the specified plate. This attribute is only active for
plates of property type load patch.

**Syntax**

```c
long St7SetPlateLoadPatch4(long uID, long PlateNum, long
PatchType, long EdgeBits, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `PatchType` — Load patch type, one of ptAuto4, ptAuto3, ptAuto2, ptAuto1, ptAngleSplit or ptManual.
- `EdgeBits` — A 32-bit word in which the four least significant bits specify the selection of up to four edges. See Load Patch Types for additional information.
- `Doubles[0..3]` — Edge weights, see Load Patch Types for additional information.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_InvalidPatchType,
ERR7_InvalidPatchTypeForPlate, ERR7_InvalidPlateEdge,
ERR7_InvalidUCSID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SetPlateReinforcement2`

Assigns the concrete reinforcement properties for the specified plate.

**Syntax**

```c
long St7SetPlateReinforcement2(long uID, long PlateNum,
long LayoutID, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `LayoutID` — Reinforcement layout ID number.
- `Doubles[0..1]` — A 2 element array describing the angular orientation of the 1-3 and 2-4 reinforcement layers respectively.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidLayoutID,
ERR7_InvalidUCSID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SetPlateCreepLoadingAge1`

Sets the creep loading age for the specified plate. This attribute is only active
when conducting creep analysis using the Quasi-Static solver.

**Syntax**

```c
long St7SetPlateCreepLoadingAge1(long uID, long PlateNum,
double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `Doubles[0]` — Creep loading age in seconds.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetPlateEdgeAttachment1`

Assigns an edge attachment to the specified plate edge. Attachment attributes
can be used to generate attachment links using the St7ToolAttachParts function.

**Syntax**

```c
long St7SetPlateEdgeAttachment1(long uID, long PlateNum,
long EdgeNum, long Direction, long AttachType, long
ConnectType, long PropNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `EdgeNum` — Local edge number, one of 1, 2, 3 or 4.
- `Direction` — Direction of attachment, one of adPlanar, adPlusZ or adMinusZ.
- `AttachType` — Attachment type, one of alDirect, alRigid or alFlexible.
- `ConnectType` — Attachment sub-type, either alMoment or alPinned.
- `PropNum` — Beam property number used for flexible attachment types.
- `Doubles[0]` — The maximum distance within which the plate edge can be connected to another element using the attachment link.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidAttachmentDirection,
ERR7_InvalidAttachmentType, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidPlateEdge,
ERR7_InvalidUCSID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SetPlateFaceAttachment1`

Assigns a face attachment to the specified plate face. Attachment attributes
can be used to generate attachment links using the St7ToolAttachParts function.
