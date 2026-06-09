---
title: "Vertex Attributes – Set"
source: "Strand7 R246 API Manual"
pages: 417–430
---

# Vertex Attributes – Set

Brick Attributes – Get
Attachment sub-type, either alMoment or alPinned.

PropNum
Beam property number used for flexible attachment types.

Doubles[0]
The maximum distance within which the brick face can be connected to
another element using the attachment link.
Errors

ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen


---

### `St7SetVertexType`

Sets the type for the specified vertex.

**Syntax**

```c
long St7SetVertexType(long uID, long VertexNum, long
VertexType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `VertexNum` — Vertex number.
- `VertexType` — Vertex type, either vtFree or vtFixed.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidVertexType, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetVertexID`

Assigns an ID number to the specified vertex.

**Syntax**

```c
long St7SetVertexID(long uID, long VertexNum, long
VertexID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `VertexNum` — Vertex number.
- `VertexID` — Vertex ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SetVertexMeshSize1`

Assigns a desired mesh size at the specified vertex. This value is used to control
the local mesh resolution when using the surface automeshing tools.

**Syntax**

```c
long St7SetVertexMeshSize1(long uID, long VertexNum,
double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `VertexNum` — Vertex number.
- `Doubles[0]` — Desired mesh size at the specified vertex. This value is used to determine the desired edge length of adjacent plate elements generated during surface auto-meshing.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SetVertexRestraint6`

Assigns structural restraint conditions at the specified vertex.

**Syntax**

```c
long St7SetVertexRestraint6(long uID, long VertexNum, long
CaseNum, long UCSId, long* Status, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `VertexNum` — Vertex number.
- `CaseNum` — Load case number.
- `UCSId` — UCS ID number.
- `Status[0..5]` — An array describing the restraint conditions for the six DoF at the specified vertex. Status[i-1] = btTrue indicates that the ith DoF is restrained. The DoF are restrained according to the 123456 axis convention in the specified UCS.
- `Doubles[0..5]` — An array describing the enforced displacement conditions for the six DoF at the specified vertex. Doubles[i-1] describes the displacement of the ith DoF according to the 123456 axis convention in the specified UCS.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidUCSID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SetVertexForce3`

Assigns a point force to the specified vertex.

**Syntax**

```c
long St7SetVertexForce3(long uID, long VertexNum, long
CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `VertexNum` — Vertex number.
- `CaseNum` — Load case number.
- `Doubles[0..2]` — A 3 element array describing the force in the XYZ Cartesian coordinate system for the specified vertex.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetVertexMoment3`

Assigns a point moment to the specified vertex.

**Syntax**

```c
long St7SetVertexMoment3(long uID, long VertexNum, long
CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `VertexNum` — Vertex number.
- `CaseNum` — Load case number.
- `Doubles[0..2]` — A 3 element array describing the moments about the XYZ Cartesian coordinate system for the specified vertex.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetVertexTemperature1`

Assigns a temperature to the specified vertex. This attribute is used when
performing both structural and heat transfer analysis.

**Syntax**

```c
long St7SetVertexTemperature1(long uID, long VertexNum,
long CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `VertexNum` — Vertex number.
- `CaseNum` — Load case number.
- `Doubles[0]` — Temperature value at the specified vertex.

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

### `St7SetVertexTemperatureType1`

Sets the temperature type assigned at the specified vertex. This attribute is used
when performing both structural and heat transfer analysis.

**Syntax**

```c
long St7SetVertexTemperatureType1(long uID, long VertexNum,
long CaseNum, long tType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `VertexNum` — Vertex number.
- `CaseNum` — Load case number.
- `tType` — The type of temperature attribute applied at the specified node, one of tReferenceTemperature, tFixedTemperature, tInitialTemperature or tTableTemperature.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,


ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_InvalidTemperatureType,
ERR7_InvalidUCSID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SetVertexTemperatureTable`

Specifies the table to be associated with the temperature assigned to the
specified vertex. This attribute is used when performing both structural and heat
transfer analysis.

**Syntax**

```c
long St7SetVertexTemperatureTable(long uID, long VertexNum,
long CaseNum, long TableID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `VertexNum` — Vertex number.
- `CaseNum` — Load case number.
- `TableID` — ID number for the Factor vs Time table.

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

### `St7SetVertexKTranslation3F`

Assigns a translational stiffness to the specified vertex.

**Syntax**

```c
long St7SetVertexKTranslation3F(long uID, long VertexNum,
long CaseNum, long UCSId, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `VertexNum` — Vertex number.
- `CaseNum` — Freedom case number.
- `UCSId` — UCS ID number.
- `Doubles[0..2]` — A 3 element array describing the translational stiffnesses for the specified vertex. Doubles[i-1] describes the stiffness for the ith translational DoF according to the 123 axis definition in the specified UCS.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetVertexKRotation3F`

Assigns a rotational stiffness to the specified vertex.

**Syntax**

```c
long St7SetVertexKRotation3F(long uID, long VertexNum, long
CaseNum, long UCSId, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `VertexNum` — Vertex number.
- `CaseNum` — Freedom case number.
- `UCSId` — UCS ID number.
- `Doubles[0..2]` — A 3 element array describing the rotational stiffnesses for the specified vertex. Doubles[i-1] describes the stiffness for the ith rotational DoF according to the 456 axis definition in the specified UCS.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetVertexTMass3`

Assigns a translational mass to the specified vertex.

**Syntax**

```c
long St7SetVertexTMass3(long uID, long VertexNum, double*
Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `VertexNum` — Vertex number.
- `Doubles[0..2]` — A 3 element array describing the translational mass for the specified vertex. Doubles[i-1] describes the translational mass for the ith translational DoF according to the XYZ Cartesian axis convention.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetVertexRMass3`

Assigns a rotational mass to the specified vertex.

**Syntax**

```c
long St7SetVertexRMass3(long uID, long VertexNum, long
UCSId, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `VertexNum` — Vertex number.
- `UCSId` — UCS ID number.
- `Doubles[0..2]` — A 3 element array describing the rotational mass for the specified vertex. Doubles[i-1] describes the rotational mass for the ith rotational DoF according to the 456 axis convention in the specified UCS.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetVertexNSMass5`

Assigns a non-structural mass to the specified vertex.

**Syntax**

```c
long St7SetVertexNSMass5(long uID, long VertexNum, long
CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `VertexNum` — Vertex number.
- `CaseNum` — Load case number.
- `Doubles[0..4]` — [0] - Non-structural mass at the specified vertex. [1] - Dynamic factor for the specified vertex. This factor is used to scale the non-structural mass when performing dynamic analysis. [2..4] - A 3 element array describing the offset in the XYZ Cartesian coordinate system.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetVertexKDamping3F`

Assigns the translational damping coefficients for the specified vertex.

**Syntax**

```c
long St7SetVertexKDamping3F(long uID, long VertexNum, long
CaseNum, long UCSId, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `VertexNum` — Vertex number.
- `CaseNum` — Load case number.
- `UCSId` — UCS ID number.
- `Doubles[0..2]` — A 3 element array describing the damping factors for the specified vertex. Doubles[i-1] describes the damping factor for the ith translational DoF according to the 123 axis definition in the specified UCS.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetVertexHeatSource1`

Assigns a thermal heat source to the specified vertex. This attribute is only used
when performing heat transfer analysis.

**Syntax**

```c
long St7SetVertexHeatSource1(long uID, long VertexNum, long
CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `VertexNum` — Vertex number.
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

### `St7SetVertexHeatSourceTables`

Specifies the tables to be associated with the thermal source assigned to the
specified vertex. Both Factor vs Time and Factor vs Temperature tables may be
assigned. This attribute is only used when performing heat transfer analysis.

**Syntax**

```c
long St7SetVertexHeatSourceTables(long uID, long VertexNum,
long CaseNum, long* Tables)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
