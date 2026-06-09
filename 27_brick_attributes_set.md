---
title: "Brick Attributes – Set"
source: "Strand7 R246 API Manual"
pages: 376–395
---

# Brick Attributes – Set

PropNum
Beam property number used for flexible attachment types.

Doubles[0]
The maximum distance within which the plate face can be connected to
another element using the attachment link.
Errors

ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen


---

### `St7SetBrickID`

Sets the ID number for the specified brick.

**Syntax**

```c
long St7SetBrickID(long uID, long BrickNum, long BrickID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BrickNum` — Brick number.
- `BrickID` — Brick ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SetBrickLocalAxes1`

Aligns the brick local axis system with a specified UCS. See Brick Local
Coordinates for further information.

**Syntax**

```c
long St7SetBrickLocalAxes1(long uID, long BrickNum, long
UCSId)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BrickNum` — Brick number.
- `UCSId` — UCS ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetBrickSupport1F`

Sets the elastic support conditions for the specified brick face. The support acts
normal to the plane of the face and is constant over the surface.

**Syntax**

```c
long St7SetBrickSupport1F(long uID, long BrickNum, long
FaceNum, long CaseNum, long Status, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BrickNum` — Brick number.
- `FaceNum` — Local face number, see Brick Local Coordinates.
- `CaseNum` — Load case number.
- `Status` — Compression-only support, either btTrue or btFalse.
- `Doubles[0]` — Elastic support value.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidBrickFace,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidUCSID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SetBrickPreLoad3`

Sets the pre-load conditions for the specified brick. The pre-loads are applied
according to the orientation of the brick local axis system.

**Syntax**

```c
long St7SetBrickPreLoad3(long uID, long BrickNum, long
CaseNum, long LoadType, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BrickNum` — Brick number.
- `CaseNum` — Load case number.
- `LoadType` — plBrickPreStress or plBrickPreStrain.
- `Doubles[0..2]` — A 3 element array describing the pre-load magnitudes according to the orientation of the local brick axis system.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,


ERR7_InvalidLoadCase, ERR7_InvalidPreLoadType,
ERR7_InvalidUCSID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SetBrickPointForce6`

Assigns a point force to the specified brick face.

**Syntax**

```c
long St7SetBrickPointForce6(long uID, long BrickNum, long
FaceNum, long CaseNum, long Position, long ID, double*
Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BrickNum` — Brick number.
- `FaceNum` — Local face number. See Brick Local Coordinates for additional information.
- `CaseNum` — Load case number.
- `Position` — Position identifier, either axUCS or axLocal.
- `ID` — Point force ID number.
- `Doubles[0..5]` — [0..2] - Components of applied force in the Global Cartesian coordinate system. axUCS: [3..5] - XYZ position of applied force in the Global Cartesian coordinate system. axLocal: [3..4] - UV position of applied force in the local element coordinate system.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidBrickFace,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_InvalidPositionType,
ERR7_InvalidUCSID, ERR7_InvalidUVPos, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetBrickNormalPressure1`

Assigns a pressure to the specified brick face. The pressure acts into the element,
normal to the plane of the face and is constant over the surface.

**Syntax**

```c
long St7SetBrickNormalPressure1(long uID, long BrickNum,
long FaceNum, long CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BrickNum` — Brick number.
- `FaceNum` — Local face number. See Brick Local Coordinates for additional information.
- `CaseNum` — Load case number.
- `Doubles[0]` — Normal pressure.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidBrickFace,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidUCSID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SetBrickGlobalPressure3`

Assigns a pressure to the specified brick face in the Global Cartesian Coordinate
system. The pressure is constant over the face surface.

**Syntax**

```c
long St7SetBrickGlobalPressure3(long uID, long BrickNum,
long FaceNum, long ProjectFlag, long CaseNum, double*
Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BrickNum` — Brick number.
- `FaceNum` — Local face number. See Brick Local Coordinates for additional information.
- `ProjectFlag` — Either btTrue or btFalse to project the global pressure components.
- `CaseNum` — Load case number.
- `Doubles[0..2]` — A 3 element array describing the XYZ components of the applied pressure in the Global Cartesian Coordinate system.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidBrickFace,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidUCSID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SetBrickShear2`

Assigns a shear stress to the specified brick face. The shear stress acts in the plane
of the face and is constant over the surface.

**Syntax**

```c
long St7SetBrickShear2(long uID, long BrickNum, long
FaceNum, long CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BrickNum` — Brick number.
- `FaceNum` — Local face number. See Brick Local Coordinates for additional information.
- `CaseNum` — Load case number.
- `Doubles[0..1]` — A 2 element array describing the shear stress components in the local face XY axis system.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidBrickFace,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidUCSID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SetBrickNSMass5`

Assigns a non-structural mass to the specified brick.

**Syntax**

```c
long St7SetBrickNSMass5(long uID, long BrickNum, long
FaceNum, long CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BrickNum` — Brick number.
- `FaceNum` — Local face number. See Brick Local Coordinates for additional information.
- `CaseNum` — Load case number.
- `Doubles[0..5]` — [0] - Non-structural mass for the specified plate. [1] - Dynamic factor for the specified plate. This factor is used to scale the non-structural mass when performing dynamic analyses. [2..5] - A 3 element array describing the offset in the XYZ Global Cartesian coordinate system.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidBrickFace,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidUCSID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SetBrickConvection2`

Assigns the thermal convection coefficient and ambient temperature for the
specified brick face. This attribute is only used when performing heat transfer
analysis.

**Syntax**

```c
long St7SetBrickConvection2(long uID, long BrickNum, long
FaceNum, long CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BrickNum` — Brick number.
- `FaceNum` — Local face number. See Brick Local Coordinates for additional information.
- `CaseNum` — Load case number.
- `Doubles[0..1]` — [0] - Convection coefficient. [1] - Ambient temperature.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidBrickFace,
ERR7_InvalidEntity, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidLoadID, ERR7_InvalidUCSID,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SetBrickConvectionTables`

Specifies the tables associated with thermal convection properties assigned to
the specified brick face. A Factor vs Temperature table may apply to the
convection coefficient and Factor vs Time tables may apply to both the
convection coefficient and ambient temperature.

**Syntax**

```c
long St7SetBrickConvectionTables(long uID, long BrickNum,
long FaceNum, long CaseNum, long* Tables)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BrickNum` — Brick number.
- `FaceNum` — Local face number. See Brick Local Coordinates for additional information.
- `CaseNum` — Load case number.
- `Tables[0..2]` — [0] - Factor vs Time table ID associated with the ambient temperature, zero for none. [1] - Factor vs Temperature table ID associated with the convection coefficient, zero for none. [2] - Factor vs Time table ID associated with the convection coefficient, zero for none.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidBrickFace,
ERR7_InvalidEntity, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidLoadID,


ERR7_InvalidTableType, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_TableDoesNotExist
```


---

### `St7SetBrickRadiation2`

Assigns the thermal radiation coefficient and ambient temperature for the
specified brick face.

**Syntax**

```c
long St7SetBrickRadiation2(long uID, long BrickNum, long
FaceNum, long CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BrickNum` — Brick number.
- `FaceNum` — Local face number. See Local Bricks Faces for additional information.
- `CaseNum` — Load case number.
- `Doubles[0..1]` — [0] - Radiation coefficient. [1] - Ambient temperature.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidBrickFace,
ERR7_InvalidEntity, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidLoadID, ERR7_InvalidUCSID,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SetBrickRadiationTables`

Specifies the tables associated with the thermal radiation properties assigned to
a specified brick face. A Factor vs Temperature table may apply to the radiation
coefficient and Factor vs Time tables may apply to both the radiation coefficient
and ambient temperature.

**Syntax**

```c
long St7SetBrickRadiationTables(long uID, long BrickNum,
long FaceNum, long CaseNum, long* Tables)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BrickNum` — Brick number.
- `FaceNum` — Local face number. See Brick Local Coordinates for additional information.
- `CaseNum` — Load case number.
- `Tables[0..2]` — [0] - Factor vs Time table ID associated with the ambient temperature, use zero for none. [1] - Factor vs Temperature table ID associated with the radiation coefficient, use zero for none. [2] - Factor vs Time table ID associated with the radiation coefficient, use zero for none.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidBrickFace,
ERR7_InvalidEntity, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidLoadID,


ERR7_InvalidTableType, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_TableDoesNotExist
```


---

### `St7SetBrickFlux1`

Assigns a heat flux to the specified brick face.

**Syntax**

```c
long St7SetBrickFlux1(long uID, long BrickNum, long FaceNum,
long CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BrickNum` — Brick number.
- `FaceNum` — Local face number. See Brick Local Coordinates for additional information.
- `CaseNum` — Load case number.
- `Doubles[0]` — The heat flux through the brick face.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidBrickFace,
ERR7_InvalidEntity, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidLoadID, ERR7_InvalidUCSID,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SetBrickFluxTables`

Specifies the tables to be associated with the heat flux assigned to the specified
brick face. Both Factor vs Time and Factor vs Temperature tables may be
assigned.

**Syntax**

```c
long St7SetBrickFluxTables(long uID, long BrickNum, long
FaceNum, long CaseNum, long* Tables)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BrickNum` — Brick number.
- `FaceNum` — Local face number. See Brick Local Coordinates for additional information.
- `CaseNum` — Load case number.
- `Tables[0..1]` — [0] - Factor vs Time table ID associated with the heat flux, zero for none. [1] - Factor vs Temperature table ID associated with the heat flux, zero for none.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidBrickFace,
ERR7_InvalidEntity, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidLoadID,
ERR7_InvalidTableType, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_TableDoesNotExist
```


---

### `St7SetBrickHeatSource1`

Assigns a thermal heat source to the specified brick.

**Syntax**

```c
long St7SetBrickHeatSource1(long uID, long BrickNum, long
CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BrickNum` — Brick number.
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

### `St7SetBrickHeatSourceTables`

Specifies the tables to be associated with the heat source assigned to the
specified brick. Both a Factor vs Time and Factor vs Temperature table may be
assigned.

**Syntax**

```c
long St7SetBrickHeatSourceTables(long uID, long BrickNum,
long CaseNum, long* Tables)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BrickNum` — Brick number.
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

### `St7SetBrickSoilStress2`

Assigns the in-situ soil stress for the specified brick. This attribute is only active for
bricks of property type soil.

**Syntax**

```c
long St7SetBrickSoilStress2(long uID, long BrickNum, long
CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BrickNum` — Brick number.
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

### `St7SetBrickSoilRatio2`

Assigns the in-situ soil ratios for the specified brick. This attribute is only active for
bricks of property type soil.

**Syntax**

```c
long St7SetBrickSoilRatio2(long uID, long BrickNum, long
CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BrickNum` — Brick number.
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

### `St7SetBrickResponse`

Assigns a response variable to the specified brick. Response variables are only
used by the Load Influence solver.

**Syntax**

```c
long St7SetBrickResponse(long uID, long BrickNum, long
CaseNum, long UCSId, long* Status)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BrickNum` — Brick number.
- `CaseNum` — Load case number.
- `UCSId` — UCS ID number.
- `Status[0..5]` — A 6 element array describing which stress components are flagged as response variables according to the 123 axis convention in the specified UCS, [11, 22, 33, 12, 23, 31].

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidBeamEnd,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidLoadCase, ERR7_InvalidResponseType,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SetBrickCreepLoadingAge1`

Assigns a creep loading age for the specified brick. This attribute is only used
when performing creep analysis using the Quasi-Static solver.

**Syntax**

```c
long St7SetBrickCreepLoadingAge1(long uID, long BrickNum,
double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BrickNum` — Brick number.
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

### `St7SetBrickFaceAttachment1`

Assigns an attachment to the specified brick face. Attachment attributes can be
used to generate attachment links using the St7ToolAttachParts function.
