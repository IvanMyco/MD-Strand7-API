---
title: "Face Attributes – Set"
source: "Strand7 R246 API Manual"
pages: 469–481
---

# Face Attributes – Set

Edge Attributes – Get

ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen


---

### `St7SetGeometryFaceProperty`

Assigns a property number to the specified geometry face.

**Syntax**

```c
long St7SetGeometryFaceProperty(long uID, long FaceNum,
long PropNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FaceNum` — Face number.
- `PropNum` — Property number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidPropertyNumber, ERR7_InvalidFileUnit,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SetGeometryFaceID`

Assigns an ID number to the specified geometry face.

**Syntax**

```c
long St7SetGeometryFaceID(long uID, long FaceNum, long
FaceID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FaceNum` — Face number.
- `FaceID` — Face ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SetGeometryFaceOffset1`

Assigns an offset to the specified geometry face. This value is constant over the
surface.

**Syntax**

```c
long St7SetGeometryFaceOffset1(long uID, long FaceNum,
double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FaceNum` — Face number.
- `Doubles[0]` — Offset value.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetGeometryFaceSupport1F`

Assigns an elastic support condition to the specified geometry face.

**Syntax**

```c
long St7SetGeometryFaceSupport1F(long uID, long FaceNum,
long CaseNum, long Status, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FaceNum` — Face number.
- `CaseNum` — Freedom case number.
- `Status` — Compression-only flag, either btTrue or btFalse.
- `Doubles[0]` — Elastic support value.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetGeometryFaceTempGradient1`

Assigns a temperature gradient to the specified geometry face. This attribute is
only used when performing structural analysis.

**Syntax**

```c
long St7SetGeometryFaceTempGradient1(long uID, long FaceNum,
long CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FaceNum` — Face number.
- `CaseNum` — Load case number.
- `Doubles[0]` — Temperature gradient.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetGeometryFaceNormalPressure1`

Assigns a normal pressure to the specified geometry face.

**Syntax**

```c
long St7SetGeometryFaceNormalPressure1(long uID, long
FaceNum, long CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FaceNum` — Face number.
- `CaseNum` — Load case number.
- `Doubles[0]` — Normal pressure value.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetGeometryFaceGlobalPressure3`

Assigns a pressure to the specified geometry face in the Global Cartesian
Coordinate system.

**Syntax**

```c
long St7SetGeometryFaceGlobalPressure3(long uID, long
FaceNum, long ProjectFlag, long CaseNum, double*
Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FaceNum` — Face number.
- `ProjectFlag` — btTrue or btFalse.
- `CaseNum` — Load case number.
- `Doubles[0..2]` — A 3 element array describing the XYZ pressure components in the Global Cartesian Coordinate system.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetGeometryFaceNSMass5`

Assigns a non-structural mass to the specified geometry face.

**Syntax**

```c
long St7SetGeometryFaceNSMass5(long uID, long FaceNum, long
CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FaceNum` — Face number.
- `CaseNum` — Load case number.
- `Doubles[0..4]` — [0] - Non-structural mass for the specified face. [1] - Dynamic factor for the specified face. This factor is used to scale the non-structural mass when performing dynamic analysis. [2..4] - A 3 element array describing the offset in the XYZ Cartesian coordinate system.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetGeometryFaceConvection2`

Assigns the thermal convection coefficient and ambient temperature for the
specified geometry face. This attribute is only used when performing heat transfer
analysis.

**Syntax**

```c
long St7SetGeometryFaceConvection2(long uID, long FaceNum,
long CaseNum, long Surface, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FaceNum` — Face number.
- `CaseNum` — Load case number.
- `Surface` — Local plate surface, either psPlateZMinus or psPlateZPlus.
- `Doubles[0..1]` — [0] - Convection coefficient. [1] - Ambient temperature.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFaceSurface,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidLoadID, ERR7_InvalidUCSID,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SetGeometryFaceConvectionTables`

Specifies the tables associated with the thermal convection properties assigned
to a specified geometry face. A Factor vs Temperature table may apply to the
convection coefficient and Factor vs Time tables may apply to both the
convection coefficient and ambient temperature.

**Syntax**

```c
long St7SetGeometryFaceConvectionTables(long uID, long
FaceNum, long CaseNum, long Surface, long* Tables)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FaceNum` — Face number.
- `CaseNum` — Load case number.
- `Surface` — Local plate surface, either psPlateZMinus or psPlateZPlus.
- `Tables[0..2]` — [0] - Factor vs Time table ID associated with the ambient temperature, use zero for none. [1] - Factor vs Temperature table ID associated with the convection coefficient, use zero for none. [2] - Factor vs Time table ID associated with the convection coefficient, use zero for none.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFaceSurface,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidLoadID,


ERR7_InvalidTableType, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_TableDoesNotExist
```


---

### `St7SetGeometryFaceRadiation2`

Assigns the thermal radiation coefficient and ambient temperature for the
specified geometry face.

**Syntax**

```c
long St7SetGeometryFaceRadiation2(long uID, long FaceNum,
long CaseNum, long Surface, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FaceNum` — Face number.
- `CaseNum` — Load case number.
- `Surface` — Local plate surface, psPlateZMinus or psPlateZPlus.
- `Doubles[0..1]` — [0] - Radiation coefficient. [1] - Ambient temperature.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFaceSurface,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidLoadID, ERR7_InvalidUCSID,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SetGeometryFaceRadiationTables`

Specifies the tables associated with the thermal radiation properties assigned to
a specified geometry face. A Factor vs Temperature table may apply to the
radiation coefficient and Factor vs Time tables may apply to both the radiation
coefficient and ambient temperature.

**Syntax**

```c
long St7SetGeometryFaceRadiationTables(long uID, long
FaceNum, long CaseNum, long Surface, long* Tables)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FaceNum` — Face number.
- `CaseNum` — Load case number.
- `Surface` — Local plate surface, psPlateZMinus or psPlateZPlus.
- `Tables[0..2]` — [0] - Factor vs Time table ID associated with the ambient temperature, use zero for none. [1] - Factor vs Temperature table ID associated with the radiation coefficient, use zero for none. [2] - Factor vs Time table ID associated with the radiation coefficient, use zero for none.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFaceSurface,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidLoadID,


ERR7_InvalidTableType, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_TableDoesNotExist
```


---

### `St7SetGeometryFaceHeatSource1`

Assigns a thermal heat source to the specified geometry face.

**Syntax**

```c
long St7SetGeometryFaceHeatSource1(long uID, long FaceNum,
long CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FaceNum` — Face number.
- `CaseNum` — Load case number.
- `Doubles[0]` — Heat source value.

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

### `St7SetGeometryFaceHeatSourceTables`

Specifies the tables associated with the thermal heat source assigned to the
specified geometry face. Both Factor vs Time and Factor vs Temperature tables


may be assigned. This attribute is only used when performing heat transfer
analysis.

**Syntax**

```c
long St7SetGeometryFaceHeatSourceTables(long uID, long
FaceNum, long CaseNum, long* Tables)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FaceNum` — Face number.
- `CaseNum` — Load case number.
- `Tables[0..1]` — [0] - Factor vs Time table ID associated with the thermal heat source, use zero for none. [1] - Factor vs Temperature table ID associated with the thermal heat source, use zero for none.

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

### `St7SetGeometryFaceAttachment1`

Assigns an attachment condition to the specified geometry face. Attachment
attributes can be sued to generate attachment links using the St7ToolAttachParts
function.
