---
title: "Vertex Attributes – Get"
source: "Strand7 R246 API Manual"
pages: 431–444
---

# Vertex Attributes – Get

Vertex Attributes – Set

VertexNum
Vertex number.

CaseNum
Load case number.

Tables[0..1]
[0] - Factor vs Time table ID associated with the heat source, use zero for
none.

[1] - Factor vs Temperature table ID associated with the heat source, use
zero for none.
Errors

ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_InvalidTableType,
ERR7_InvalidUCSID, ERR7_NoError, ERR7_ResultFileIsOpen,
ERR7_TableDoesNotExist


---

### `St7GetVertexType`

Returns the type assigned to the specified vertex.

**Syntax**

```c
long St7GetVertexType(long uID, long VertexNum, long*
VertexType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `VertexNum` — Vertex number.

**Output Parameters**

- `VertexType` — Vertex type, either vtFree or vtFixed.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7GetVertexID`

Returns the ID number assigned to the specified vertex.

**Syntax**

```c
long St7GetVertexID(long uID, long VertexNum, long*
VertexID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `VertexNum` — Vertex number.

**Output Parameters**

- `VertexID` — Vertex ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetVertexMeshSize1`

Returns the desired mesh size assigned to the specified vertex. This value is used
to control the local mesh resolution when using the surface automeshing tools.

**Syntax**

```c
long St7GetVertexMeshSize1(long uID, long VertexNum,
double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `VertexNum` — Vertex number.

**Output Parameters**

- `Doubles[0]` — Desired mesh size at the specified vertex. This value is used to determine the desired edge length of adjacent plate elements generated during surface auto-meshing.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7GetVertexRestraint6`

Returns the restraint conditions assigned at the specified vertex.

**Syntax**

```c
long St7GetVertexRestraint6(long uID, long VertexNum, long
CaseNum, long* UCSId, long* Status, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `VertexNum` — Vertex number.
- `CaseNum` — Load case number.

**Output Parameters**

- `UCSId` — UCS ID number.
- `Status[0..5]` — An array describing the restraint conditions for the six DoF at the specified vertex. Status[i-1] = btTrue indicates that the ith DoF is restrained. The DoF are restrained according to the 123456 axis convention in the specified UCS.
- `Doubles[0..5]` — An array describing the enforced displacement conditions for the six DoF at the specified vertex. Doubles[i-1] describes the displacement of the ith DoF according to the 123456 axis convention in the specified UCS.

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

### `St7GetVertexForce3`

Returns the point force assigned to the specified vertex.

**Syntax**

```c
long St7GetVertexForce3(long uID, long VertexNum, long
CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `VertexNum` — Vertex number.
- `CaseNum` — Load case number.

**Output Parameters**

- `Doubles[0..2]` — A 3 element array describing the force in the XYZ Cartesian coordinate system for the specified vertex.

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

### `St7GetVertexMoment3`

Returns the point moment assigned at the specified vertex.

**Syntax**

```c
long St7GetVertexMoment3(long uID, long VertexNum, long
CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `VertexNum` — Vertex number.
- `CaseNum` — Load case number.

**Output Parameters**

- `Doubles[0..2]` — A 3 element array describing the moments about the XYZ Cartesian coordinate system for the specified vertex.

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

### `St7GetVertexTemperature1`

Returns the temperature assigned to the specified vertex. This attribute is used
when conducting both structural and heat transfer analysis.

**Syntax**

```c
long St7GetVertexTemperature1(long uID, long VertexNum,
long CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `VertexNum` — Vertex number.
- `CaseNum` — Load case number.

**Output Parameters**

- `Doubles[0]` — Applied temperature value.

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

### `St7GetVertexTemperatureType1`

Returns the temperature type assigned to the specified vertex. This attribute is
used when performing both structural and heat transfer analysis.

**Syntax**

```c
long St7GetVertexTemperatureType1(long uID, long VertexNum,
long CaseNum, long* tType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `VertexNum` — Vertex number.
- `CaseNum` — Load case number.

**Output Parameters**

- `tType` — The type of temperature attribute applied at the specified node, one of tReferenceTemperature, tFixedTemperature, tInitialTemperature or tTableTemperature.

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

### `St7GetVertexTemperatureTable`

Returns the table associated with the specified vertex. This attribute is used when
performing both structural and heat transfer analysis.

**Syntax**

```c
long St7GetVertexTemperatureTable(long uID, long VertexNum,
long CaseNum, long* TableID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `VertexNum` — Vertex number.
- `CaseNum` — Load case number.

**Output Parameters**

- `TableID` — ID number for the Factor vs Time table associated with the assigned temperature.

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

### `St7GetVertexKTranslation3F`

Returns the translational stiffness assigned to the specified vertex.

**Syntax**

```c
long St7GetVertexKTranslation3F(long uID, long VertexNum,
long CaseNum, long* UCSId, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `VertexNum` — Vertex number.
- `CaseNum` — Freedom case number.

**Output Parameters**

- `UCSId` — UCS ID number.
- `Doubles[0..2]` — A 3 element array describing the translational stiffnesses for the specified vertex. Doubles[i-1] describes the stiffness for the ith translational DoF according to the 123 axis definition in the specified UCS.

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

### `St7GetVertexKRotation3F`

Returns the rotational stiffness assigned to the specified vertex.

**Syntax**

```c
long St7GetVertexKRotation3F(long uID, long VertexNum, long
CaseNum, long* UCSId, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `VertexNum` — Vertex number.
- `CaseNum` — Freedom case number.

**Output Parameters**

- `UCSId` — UCS ID number.
- `Doubles[0..2]` — A 3 element array describing the rotational stiffnesses for the specified vertex. Doubles[i-1] describes the stiffness for the ith rotational DoF according to the 456 axis definition in the specified UCS.

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

### `St7GetVertexTMass3`

Returns the translational mass assigned to the specified vertex.

**Syntax**

```c
long St7GetVertexTMass3(long uID, long VertexNum, double*
Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `VertexNum` — Vertex number.

**Output Parameters**

- `Doubles[0..2]` — A 3 element array describing the translational mass for the specified vertex. Doubles[i-1] describes the translational mass for the ith translational DoF according to the XYZ Cartesian axis convention.

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

### `St7GetVertexRMass3`

Returns the rotational mass assigned to the specified vertex.

**Syntax**

```c
long St7GetVertexRMass3(long uID, long VertexNum, long*
UCSId, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `VertexNum` — Vertex number.

**Output Parameters**

- `UCSId` — UCS ID number.
- `Doubles[0..2]` — A 3 element array describing the rotational mass for the specified vertex. Doubles[i-1] describes the rotational mass for the ith rotational DoF according to the 456 axis convention in the specified UCS.

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

### `St7GetVertexNSMass5`

Returns the non-structural mass assigned to the specified vertex.

**Syntax**

```c
long St7GetVertexNSMass5(long uID, long VertexNum, long
CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `VertexNum` — Vertex number.
- `CaseNum` — Load case number.

**Output Parameters**

- `Doubles[0..4]` — [0] - Non-structural mass at the specified vertex. [1] - Dynamic factor for the specified vertex. This factor is used to scale the non-structural mass when performing dynamic analysis. [2..4] - A 3 element array describing the offset in the XYZ Cartesian coordinate system.

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

### `St7GetVertexKDamping3F`

Returns the translational damping coefficients assigned to the specified vertex.

**Syntax**

```c
long St7GetVertexKDamping3F(long uID, long VertexNum, long
CaseNum, long* UCSId, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `VertexNum` — Vertex number.
- `CaseNum` — Freedom case number.

**Output Parameters**

- `UCSId` — UCS ID number.
- `Doubles[0..2]` — A 3 element array describing the damping factors for the specified vertex. Doubles[i-1] describes the damping factor for the ith translational DoF according to the 123 axis definition in the specified UCS.

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

### `St7GetVertexHeatSource1`

Returns the thermal heat source assigned to the specified vertex. This attribute is
only used when performing heat transfer analysis.

**Syntax**

```c
long St7GetVertexHeatSource1(long uID, long VertexNum, long
CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `VertexNum` — Vertex number.
- `CaseNum` — Load case number.

**Output Parameters**

- `Doubles[0]` — Heat source value.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
```
