---
title: "Plate Attributes – Get"
source: "Strand7 R246 API Manual"
pages: 340–375
---

# Plate Attributes – Get

Syntax

long St7SetPlateFaceAttachment1(long uID, long PlateNum,
long Surface, long AttachType, long ConnectType, long
PropNum, double* Doubles)
Input Parameters

uID
Strand7 model file ID number.

PlateNum
Plate number.

Surface
Local plate surface, either psPlateZMinus or psPlateZPlus.

AttachType
Attachment type, one of alDirect, alRigid or alFlexible.

ConnectType
Attachment sub-type, either alMoment or alPinned.

PropNum
Beam property number used for flexible attachment types.

Doubles[0]
The maximum distance within which the plate face can be connected to
another element using the attachment link.
Errors

ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidAttachmentType,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidPlateSurface, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen


---

### `St7GetPlateID`

Returns the ID number for the specified plate.

**Syntax**

```c
long St7GetPlateID(long uID, long PlateNum, long* PlateID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.

**Output Parameters**

- `PlateID` — Plate ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetPlateXAngle1`

Returns the local axis angle for the specified plate. This angle controls the
rotations of the plate local XY axes about the local Z axis.

**Syntax**

```c
long St7GetPlateXAngle1(long uID, long PlateNum, double*
Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.

**Output Parameters**

- `Doubles[0]` — The angle describing the rotation of the plate local axis system about the local Z axis. See Plate Local Coordinates for further information.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetPlateThickness2`

Returns the thickness attribute of the specified plate, if the thickness attribute is
set – see St7GetPlateThickness to get the default plate property thickness.

**Syntax**

```c
long St7GetPlateThickness2(long uID, long PlateNum, double*
Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.

**Output Parameters**

- `Doubles[0..1]` — [0] - Plate membrane thickness. [1] - Plate bending thickness.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetPlateOffset1`

Returns the offset for the specified plate. The offset is applied according to the
plate local Z axis direction and is uniform over the element surface.

**Syntax**

```c
long St7GetPlateOffset1(long uID, long PlateNum, double*
Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.

**Output Parameters**

- `Doubles[0]` — Plate offset in the local Z axis direction.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetPlateEdgeSupport1F`

Returns the elastic support applied at the specified plate edge. The support acts
normal to the specified edge and is uniform along the edge length.

**Syntax**

```c
long St7GetPlateEdgeSupport1F(long uID, long PlateNum, long
CaseNum, long EdgeNum, long* Status, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `CaseNum` — Load case number.
- `EdgeNum` — Local edge number, one of 1, 2, 3 or 4.

**Output Parameters**

- `Status` — Compression-only flag, either btTrue or btFalse.
- `Doubles[0]` — Elastic support value.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetPlateFaceSupport1F`

Returns the elastic support applied at the specified plate face. The support acts
according to the local plate Z axis direction and is constant over the element
surface.

**Syntax**

```c
long St7GetPlateFaceSupport1F(long uID, long PlateNum, long
CaseNum, long* Status, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `CaseNum` — Load case number.

**Output Parameters**

- `Status` — Compression-only flag, either btTrue or btFalse.
- `Doubles[0]` — Elastic support value.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetPlateEdgeRelease1`

Returns the edge release condition for the specified plate edge

**Syntax**

```c
long St7GetPlateEdgeRelease1(long uID, long PlateNum, long
EdgeNum, long* Status)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `EdgeNum` — Local edge number, either 1, 2, 3 or 4.

**Output Parameters**

- `Status[0]` — Edge release condition, either btTrue or btFalse.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetPlatePreLoad3`

Returns the pre-load conditions for the specified plate.

**Syntax**

```c
long St7GetPlatePreLoad3(long uID, long PlateNum, long
CaseNum, long* LoadType, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `CaseNum` — Load case number.

**Output Parameters**

- `LoadType` — Pre-load type, either plPlatePreStrain or plPlatePreStress.
- `Doubles[0..2]` — A 3 element array describing the pre-load condition. Doubles[i-1] describes the pre-load in the ith local axis direction.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetPlateTempGradient1`

Returns the temperature gradient for the specified plate face. The temperature
gradient acts according to the plate local Z axis direction and is constant over
the element surface. This attribute is only active for static and dynamic structural
analysis.

**Syntax**

```c
long St7GetPlateTempGradient1(long uID, long PlateNum, long
CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `CaseNum` — Load case number.

**Output Parameters**

- `Doubles[0]` — Temperature gradient in the local Z axis direction.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetPlatePointForce6`

Returns the point force assigned to the specified plate.

**Syntax**

```c
long St7GetPlatePointForce6(long uID, long PlateNum, long
CaseNum, long Position, long ID, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `CaseNum` — Load case number.
- `Position` — Position identifier, either axUCS or axLocal.
- `ID` — Local ID number for the point force.

**Output Parameters**

- `Doubles[0..5]` — [0..2] - Components of applied force in the Global Cartesian coordinate system. axUCS: [3..5] - XYZ position of point force in the Global Cartesian coordinate system. axLocal: [3..4] - UV position of point force in the local element coordinate system.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_InvalidPositionType, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetPlatePointMoment6`

Returns the point moment assigned to the specified plate.

**Syntax**

```c
long St7GetPlatePointMoment6(long uID, long PlateNum, long
CaseNum, long Position, long ID, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `CaseNum` — Load case number.
- `Position` — Position identifier, either axUCS or axLocal.
- `ID` — Local ID number for the point moment.

**Output Parameters**

- `Doubles[0..5]` — [0..2] - Components of applied moment in the Global Cartesian coordinate system. axUCS: [3..5] - XYZ position of point moment in the Global Cartesian coordinate system. axLocal: [3..4] - UV position of point moment in the local element coordinate system.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_InvalidPositionType, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetPlateEdgePressure1`

Returns the edge pressure assigned to the specified plate edge. The pressure is
applied in the plane of the element, perpendicular to the plate edge.

**Syntax**

```c
long St7GetPlateEdgePressure1(long uID, long PlateNum, long
CaseNum, long EdgeNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number
- `CaseNum` — Load case number.
- `EdgeNum` — Local edge number, one of 1, 2, 3 or 4.

**Output Parameters**

- `Doubles[0]` — Edge pressure for the plate edge, with positive pressure directed away from the plate.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetPlateEdgeShear1`

Returns the shear stress assigned to the specified plate edge. The shear stress is
applied tangential to the plate edge.

**Syntax**

```c
long St7GetPlateEdgeShear1(long uID, long PlateNum, long
CaseNum, long EdgeNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `CaseNum` — Load case number.
- `EdgeNum` — Local edge number, one of 1, 2, 3 or 4.

**Output Parameters**

- `Doubles[0]` — Edge shear stress.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetPlateEdgeNormalShear1`

Returns the shear stress assigned to the specified plate edge. The shear stress acts
normal to the plate surface at its edge, in the local +Z direction.

**Syntax**

```c
long St7GetPlateEdgeNormalShear1(long uID, long PlateNum,
long CaseNum, long EdgeNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `CaseNum` — Load case number.
- `EdgeNum` — Local edge number, one of 1, 2, 3 or 4.

**Output Parameters**

- `Doubles[0]` — Edge normal shear stress.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetPlateNormalPressure1`

Returns the normal pressure assigned to the specified plate. The pressure acts
according to the plate local Z axis direction.

**Syntax**

```c
long St7GetPlateNormalPressure1(long uID, long PlateNum,
long CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `CaseNum` — Load case number.

**Output Parameters**

- `Doubles[0]` — Plate normal pressure.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,


ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetPlateGlobalPressure3`

Returns the global pressure components assigned to the specified plate.

**Syntax**

```c
long St7GetPlateGlobalPressure3(long uID, long PlateNum,
long CaseNum, long* ProjectFlag, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `CaseNum` — Load case number.

**Output Parameters**

- `ProjectFlag` — btTrue or btFalse.
- `Doubles[0..2]` — A 3 element array describing the XYZ components of the applied pressure in the Global Cartesian Coordinate system.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetPlateShear2`

Returns the shear stress assigned to the specified plate face. The shear stress is
applied in the plane of the element.

**Syntax**

```c
long St7GetPlateShear2(long uID, long PlateNum, long
CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `CaseNum` — Load case number.

**Output Parameters**

- `Doubles[0..1]` — A 2 element array that describes the applied shear stress according to the local plate XY axis system.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetPlateNSMass5`

Returns the non-structural mass assigned to the specified plate.

**Syntax**

```c
long St7GetPlateNSMass5(long uID, long PlateNum, long
CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `CaseNum` — Load case number.

**Output Parameters**

- `Doubles[0..5]` — [0] - Non-structural mass for the specified plate. [1] - Dynamic factor for the specified plate. This factor is used to scale the non-structural mass when performing dynamic analyses. [2..5] - A 3 element array describing the offset in the XYZ Global Cartesian coordinate system.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetPlateEdgeConvection2`

Returns the edge thermal convection coefficient and ambient temperature
assigned to the specified plate. This attribute is only used when performing heat
transfer analysis.

**Syntax**

```c
long St7GetPlateEdgeConvection2(long uID, long PlateNum,
long CaseNum, long EdgeNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `CaseNum` — Load case number.
- `EdgeNum` — Local edge number, one of 1, 2, 3 or 4.

**Output Parameters**

- `Doubles[0..1]` — [0] - Convection coefficient. [1] - Ambient temperature.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetPlateEdgeConvectionTables`

Returns the tables associated with thermal convection properties assigned to the
specified plate edge. A Factor vs Temperature table may apply to the
convection coefficient and Factor vs Time tables may apply to both the
convection coefficient and ambient temperature.

**Syntax**

```c
long St7GetPlateEdgeConvectionTables(long uID, long
PlateNum, long CaseNum, long EdgeNum, long* Tables)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `CaseNum` — Load case number.
- `EdgeNum` — Local edge number, one of 1, 2, 3 or 4.

**Output Parameters**

- `Tables[0..2]` — [0] - Factor vs Time table ID associated with the ambient temperature, use zero for none. [1] - Factor vs Temperature table ID associated with the edge convection coefficient, use zero for none. [2] - Factor vs Time table ID associated with the edge convection coefficient, use zero for none.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetPlateEdgeRadiation2`

Returns the thermal radiation coefficient and ambient temperature assigned to
the specified plate edge.

**Syntax**

```c
long St7GetPlateEdgeRadiation2(long uID, long PlateNum,
long CaseNum, long EdgeNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `CaseNum` — Load case number.
- `EdgeNum` — Local edge number.

**Output Parameters**

- `Doubles[0..1]` — [0] - Radiation coefficient. [1] - Ambient temperature.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetPlateEdgeRadiationTables`

Returns the tables associated with the thermal radiation properties assigned to a
specified plate edge. A Factor vs Temperature table may apply to the radiation
coefficient and Factor vs Time tables may apply to both the radiation coefficient
and ambient temperature.

**Syntax**

```c
long St7GetPlateEdgeRadiationTables(long uID, long PlateNum,
long CaseNum, long EdgeNum, long* Tables)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `CaseNum` — Load case number.
- `EdgeNum` — Local edge number, one of 1, 2, 3 or 4.

**Output Parameters**

- `Tables[0..2]` — [0] - Table ID number for the Factor vs Time table associated with the radiation coefficient. [1] - Table ID number for the Factor vs Temperature table associated with the radiation coefficient. [2] - Table ID number for the Factor vs Time table associated with the ambient temperature.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,


ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetPlateFlux1`

Returns the heat flux assigned to the specified plate edge.

**Syntax**

```c
long St7GetPlateFlux1(long uID, long PlateNum, long CaseNum,
long EdgeNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `CaseNum` — Load case number.
- `EdgeNum` — Local edge number, one of 1, 2, 3 or 4.

**Output Parameters**

- `Doubles[0]` — The heat flux through the plate edge.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetPlateFluxTables`

Returns the tables associated with the heat flux assigned to the specified plate
edge. Both a Factor vs Time and Factor vs Temperature table may be assigned.

**Syntax**

```c
long St7GetPlateFluxTables(long uID, long PlateNum, long
CaseNum, long EdgeNum, long* Tables)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `CaseNum` — Load case number.
- `EdgeNum` — Local edge number, one of 1, 2, 3 or 4.

**Output Parameters**

- `Tables[0..1]` — [0] - Factor vs Time table ID associated with the edge heat flux, use zero for none. [1] - Factor vs Temperature table ID associated with the edge heat flux, use zero for none.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetPlateFaceConvection2`

Returns the thermal convection coefficient and ambient temperature assigned
to the specified plate. This attribute is only used when performing heat transfer
analysis.

**Syntax**

```c
long St7GetPlateFaceConvection2(long uID, long PlateNum,
long CaseNum, long Surface, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `CaseNum` — Load case number.
- `Surface` — Local plate surface, either psPlateZMinus or psPlateZPlus.

**Output Parameters**

- `Doubles[0..1]` — [0] - Convection coefficient. [1] - Ambient temperature.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetPlateFaceConvectionTables`

Returns the tables associated with thermal convection properties assigned to the
specified plate. A Factor vs Temperature table may apply to the convection
coefficient and Factor vs Time tables may apply to both the convection
coefficient and ambient temperature.

**Syntax**

```c
long St7GetPlateFaceConvectionTables(long uID, long
PlateNum, long CaseNum, long Surface, long* Tables)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `CaseNum` — Load case number.
- `Surface` — Local plate surface, either psPlateZMinus or psPlateZPlus.

**Output Parameters**

- `Tables[0..2]` — [0] - Factor vs Time table ID associated with the ambient temperature, use zero for none. [1] - Factor vs Temperature table ID associated with the convection coefficient, use zero for none. [2] - Factor vs Time table ID associated with the convection coefficient, use zero for none.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,


ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetPlateFaceRadiation2`

Returns the thermal radiation coefficient and ambient temperature assigned to
the specified plate.

**Syntax**

```c
long St7GetPlateFaceRadiation2(long uID, long PlateNum,
long CaseNum, long Surface, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `CaseNum` — Load case number.
- `Surface` — Local plate surface, either psPlateZMinus or psPlateZPlus.

**Output Parameters**

- `Doubles[0..1]` — [0] - Radiation coefficient. [1] - Ambient temperature.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetPlateFaceRadiationTables`

Returns the tables associated with the thermal radiation properties assigned to a
specified plate. A Factor vs Temperature table may apply to the radiation
coefficient and Factor vs Time tables may apply to both the radiation coefficient
and ambient temperature.

**Syntax**

```c
long St7GetPlateFaceRadiationTables(long uID, long PlateNum,
long CaseNum, long Surface, long* Tables)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `CaseNum` — Load case number.
- `Surface` — Local plate surface, either psPlateZMinus or psPlateZPlus.

**Output Parameters**

- `Tables[0..2]` — [0] - Factor vs Time table ID associated with the ambient temperature, use zero for none. [1] - Factor vs Temperature table ID associated with the radiation coefficient, use zero for none. [2] - Factor vs Time table ID associated with the radiation coefficient, use zero for none.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,


ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetPlateHeatSource1`

Returns the thermal heat source assigned to the specified plate.

**Syntax**

```c
long St7GetPlateHeatSource1(long uID, long PlateNum, long
CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `CaseNum` — Load case number.

**Output Parameters**

- `Doubles[0]` — Thermal heat source.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetPlateHeatSourceTables`

Returns the tables associated with the thermal heat source assigned to the
specified plate. Both a Factor vs Time and Factor vs Temperature table may be
assigned.

**Syntax**

```c
long St7GetPlateHeatSourceTables(long uID, long PlateNum,
long CaseNum, long* Tables)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `CaseNum` — Load case number.

**Output Parameters**

- `Tables[0..1]` — [0] - Factor vs Time table ID associated with the heat source, use zero for none. [1] - Factor vs Temperature table ID associated with the heat source, use zero for none.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetPlateSoilStress2`

Returns the in-situ soil stress assigned to the specified plate. This attribute is only
active for plates of property type soil.

**Syntax**

```c
long St7GetPlateSoilStress2(long uID, long PlateNum, long
CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `CaseNum` — Load case number.

**Output Parameters**

- `Doubles[0..1]` — A 2 element array containing the initial vertical stress and the horizontal stress ratio.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetPlateSoilRatio2`

Returns the in-situ soil ratios assigned to the specified plate. This attribute is only
active for plates of property type soil.

**Syntax**

```c
long St7GetPlateSoilRatio2(long uID, long PlateNum, long
CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `CaseNum` — Load case number.

**Output Parameters**

- `Doubles[0..1]` — A 2 element array containing the overconsolidation ratio and the initial void ratio.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetPlateResponse`

Returns the response variable assigned to the specified plate. Response variables
are only used by the Load Influence solver.

**Syntax**

```c
long St7GetPlateResponse(long uID, long PlateNum, long
CaseNum, long* ResponseType, long* UCSId, long*
Status)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `CaseNum` — Load case number.

**Output Parameters**

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

### `St7GetPlateLoadPatch4`

Returns the load patch type assigned to the specified plate. This attribute is only
active for plates of property type load patch.

**Syntax**

```c
long St7GetPlateLoadPatch4(long uID, long PlateNum, long*
PatchType, long* EdgeBits, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.

**Output Parameters**

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
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetPlateReinforcement2`

Returns the concrete reinforcement conditions for the specified plate.

**Syntax**

```c
long St7GetPlateReinforcement2(long uID, long PlateNum,
long* LayoutID, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.

**Output Parameters**

- `LayoutID` — Layout ID number.
- `Doubles[0..1]` — A 2 element array describing the angular orientation of the 1-3 and 2-4 reinforcement layers respectively.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetPlateCreepLoadingAge1`

Returns the creep loading age assigned to the specified plate. This attribute is
only active when conducting creep analysis using the Quasi-Static solver.

**Syntax**

```c
long St7GetPlateCreepLoadingAge1(long uID, long PlateNum,
double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.

**Output Parameters**

- `Doubles[0]` — Creep loading age in seconds.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,


ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetPlateEdgeAttachment1`

Returns the attachment assigned to the specified plate edge. Attachment
attributes can be used to generate attachment links using the St7ToolAttachParts
function.

**Syntax**

```c
long St7GetPlateEdgeAttachment1(long uID, long PlateNum,
long EdgeNum, long* Direction, long* AttachType, long*
ConnectType, long* PropNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `EdgeNum` — Local edge number, one of 1, 2, 3 or 4.

**Output Parameters**

- `Direction` — Direction of attachment, one of adPlanar, adPlusZ or adMinusZ.
- `AttachType` — Attachment type, one of alDirect, alRigid or alFlexible.
- `ConnectType` — Attachment sub-type, either alMoment or alPinned.
- `PropNum` — Beam property number used for flexible attachment types.
- `Doubles[0]` — The maximum distance within which the plate edge can be connected to another element using the attachment link.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetPlateFaceAttachment1`

Returns the attachment assigned to the specified plate face. Attachment
attributes can be used to generate attachment links using the St7ToolAttachParts
function.

**Syntax**

```c
long St7GetPlateFaceAttachment1(long uID, long PlateNum,
long Surface, long* AttachType, long* ConnectType,
long* PropNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `Surface` — Local plate surface, either psPlateZMinus or psPlateZPlus.

**Output Parameters**

- `AttachType` — Attachment type, one of alDirect, alRigid or alFlexible.
- `ConnectType` — Attachment sub-type, either alMoment or alPinned.
