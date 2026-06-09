---
title: "Properties – Laminates"
source: "Strand7 R246 API Manual"
pages: 627–637
---

# Properties – Laminates

Properties – Ply

[ipLaminatePoissonxy] - Poisson’s ratio vxy.
[ipLaminatePoissonyx] - Poisson’s ratio vyx.
[ipLaminateThickness] - Thickness.
Errors

ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_UnknownProperty


---

### `St7GetTotalLaminateStacks`

Returns the total number and highest ID number of the laminate stacks in the
specified model.

**Syntax**

```c
long St7GetTotalLaminateStacks(long uID, long* NumStacks,
long* LastStack)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `NumStacks` — The total number of laminate stacks in the model.
- `LastStack` — The highest laminate number identifying a laminate stack.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7GetLaminateStackNumByIndex`

Returns the laminate number associated with a specified laminate index. The
laminate indices are stored internally and are based on a contiguous numbering
system.

**Syntax**

```c
long St7GetLaminateStackNumByIndex(long uID, long Index,
long* LaminateNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Index` — Laminate index.

**Output Parameters**

- `LaminateNum` — Laminate number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_InvalidIndex,
ERR7_NoError
```


---

### `St7NewLaminate`

Creates a new laminate.

**Syntax**

```c
long St7NewLaminate(long uID, long LamNum, char* LamName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LamNum` — Laminate number.
- `LamName` — Name of the laminate.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLaminateID, ERR7_LaminateIDAlreadyExists,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SetLaminateName`

Sets the name of the specified laminate.

**Syntax**

```c
long St7SetLaminateName(long uID, long LamNum, char*
LamName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LamNum` — Laminate number
- `LamName` — Name of the laminate.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLaminateID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetLaminateName`

Returns the name of the specified laminate.

**Syntax**

```c
long St7GetLaminateName(long uID, long LamNum, char*
LamName, long MaxStringLen)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LamNum` — Laminate number.
- `MaxStringLen` — Maximum number of characters allocated for LamName.

**Output Parameters**

- `LamName` — Name of the laminate.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLaminateID, ERR7_NoError
```


---

### `St7GetLaminateNumPlies`

Returns the number of plies in the specified laminate.

**Syntax**

```c
long St7GetLaminateNumPlies(long uID, long LamNum, long*
NumPlies)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LamNum` — Laminate number.

**Output Parameters**

- `NumPlies` — Number of plies.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLaminateID, ERR7_NoError
```


---

### `St7SetLaminatePly`

Sets the ply property and ply orientation for the specified layer in a laminate.

**Syntax**

```c
long St7SetLaminatePly(long uID, long LamNum, long Pos,
long PlyPropNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LamNum` — Laminate number.
- `Pos` — Ply position within the laminate.
- `PlyPropNum` — Ply property number.
- `Doubles[0..1]` — [ipLaminatePlyAngle] - Orientation of the ply and laminate material axis systems. [ipLaminatePlyThickness] - Ply thickness.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLaminateID, ERR7_NoError, ERR7_ResultFileIsOpen,
ERR7_UnknownProperty
```


---

### `St7GetLaminatePly`

Returns the ply property and ply orientation assigned to the specified layer in a
laminate.

**Syntax**

```c
long St7GetLaminatePly(long uID, long LamNum, long Pos,
long* PlyPropNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LamNum` — Laminate number.
- `Pos` — Ply position within the laminate.

**Output Parameters**

- `PlyPropNum` — Ply property number.
- `Doubles[0..1]` — [ipLaminatePlyAngle] - Orientation of the ply and laminate material axis systems. [ipLaminatePlyThickness] - Ply thickness.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLaminateID, ERR7_NoError
```


---

### `St7AddLaminatePly`

Adds a new ply to the specified laminate. The ply is appended to the end of the
current laminate stack.

**Syntax**

```c
long St7AddLaminatePly(long uID, long LamNum, long
PlyPropNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LamNum` — Laminate number.
- `PlyPropNum` — Ply property number.
- `Doubles[0..1]` — [ipLaminatePlyAngle] - Orientation of the ply and laminate material axis systems. [ipLaminatePlyThickness] - Ply thickness.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLaminateID, ERR7_NoError, ERR7_ResultFileIsOpen,
ERR7_UnknownProperty
```


---

### `St7InsertLaminatePly`

Inserts a new ply at the specified position within a laminate.

**Syntax**

```c
long St7InsertLaminatePly(long uID, long LamNum, long Pos,
long PlyPropNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LamNum` — Laminate number.
- `Pos` — Ply position within laminate.
- `PlyPropNum` — Ply property number.
- `Doubles[0..1]` — [ipLaminatePlyAngle] - Orientation of the ply and laminate material axis systems. [ipLaminatePlyThickness] - Ply thickness.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_ExceededMaxNumPlies,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLaminateID, ERR7_NoError, ERR7_PlyDoesNotExist,
ERR7_ResultFileIsOpen, ERR7_UnknownProperty
```


---

### `St7DeleteLaminatePly`

Deletes the specified ply from a laminate.

**Syntax**

```c
long St7DeleteLaminatePly(long uID, long LamNum, long Pos)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LamNum` — Laminate number.
- `Pos` — Ply position within laminate.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLaminateID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SetLaminateMatrices`

Sets the material matrices for the specified laminate.

**Syntax**

```c
long St7SetLaminateMatrices(long uID, long LamNum, long*
Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LamNum` — Laminate number.
- `Integers[0..1]` — [ipLaminateIgnoreCoupling] - Coupled membrane/bending option, either btTrue or btFalse. [ipLaminateAutoTransverseShear] - Automatic transverse shear calculation, either btTrue or btFalse.
- `Doubles[0..23]` — [0..2] - Transverse shear terms of the material stress-strain matrix Gxz, Gyz and Gcz respectively. [3..8] - Membrane terms C of the material stress-strain matrix defined by the coefficients C11, C12, C13, C22, C23 and C33 respectively. [9..14] - Bending terms D of the material stress-strain matrix defined by the coefficients D11, D12, D13, D22, D23 and D33 respectively. [15..23] - Coupling terms B of the material stress-strain matrix defined by the coefficients B11, B12, B13, B21, B22, B23, B31, B32 and B33 respectively.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLaminateID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetLaminateMatrices`

Returns the material matrices for the specified laminate.

**Syntax**

```c
long St7GetLaminateMatrices(long uID, long LamNum, long*
Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LamNum` — Laminate number.

**Output Parameters**

- `Integers[0..1]` — [ipLaminateIgnoreCoupling] - Coupled membrane/bending option, either btTrue or btFalse. [ipLaminateAutoTransverseShear] - Automatic transverse shear calculation, either btTrue or btFalse.
- `Doubles[0..23]` — [0..2] - Transverse shear terms of the material stress-strain matrix Gxz, Gyz and Gcz respectively. [3..8] - Membrane terms of the material stress-strain matrix defined by the coefficients C11, C12, C13, C22, C23 and C33 respectively. [9..14] - Bending terms of the material stress-strain matrix defined by the coefficients D11, D12, D13, D22, D23 and D33 respectively. [15..23] - Coupling terms of the material stress-strain matrix defined by the coefficients B11, B12, B13, B21, B22, B23, B31, B32 and B33 respectively.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLaminateID, ERR7_NoError
```
