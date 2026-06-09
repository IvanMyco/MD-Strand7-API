---
title: "Solver – Linear Static"
source: "Strand7 R246 API Manual"
pages: 738–742
---

# Solver – Linear Static

Input Parameters

uID
Strand7 model file ID number.

TableID
Table ID number.
Output Parameters

UnitType
Spectrum units type, one of fuNone, fuDispResponse, fuVelResponse,
fuAccelResponse, fuDispPSD, fuVelPSD or fuAccelPSD.
Errors

ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidTableType, ERR7_NoError, ERR7_TableDoesNotExist


---

### `St7EnableLSALoadCase`

Activates the specified load/seismic case and freedom case combination such
that it is included when performing Linear Static analysis.

**Syntax**

```c
long St7EnableLSALoadCase(long uID, long LCaseNum, long
FCaseNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LCaseNum` — Either the load case number, or the sum of the total number of load cases and the seismic case number, to indicate a load case or a seismic case respectively.
- `FCaseNum` — Freedom case number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7DisableLSALoadCase`

Deactivates the specified load/seismic case and freedom case combination
such that it is not included when performing Linear Static analysis.

**Syntax**

```c
long St7DisableLSALoadCase(long uID, long LCaseNum, long
FCaseNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LCaseNum` — Either the load case number, or the sum of the total number of load cases and the seismic case number, to indicate a load case or a seismic case respectively.
- `FCaseNum` — Freedom case number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetLSALoadCaseState`

Returns the state assigned to the specified load/seismic case and freedom case
combination for Linear Static analysis.

**Syntax**

```c
long St7GetLSALoadCaseState(long uID, long LCaseNum, long
FCaseNum, bool* State)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LCaseNum` — Either the load case number, or the sum of the total number of load cases and the seismic case number, to indicate a load case or a seismic case respectively.
- `FCaseNum` — Freedom case number.

**Output Parameters**

- `State` — btTrue if the specified load/seismic case and freedom case combination is enabled for Linear Static analysis.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7EnableLSAInitialPCGFile`

Sets the PCG solver to use the initial conditions supplied. The initial conditions are
specified using the St7SetLSAInitialPCGFile function.

**Syntax**

```c
long St7EnableLSAInitialPCGFile(long uID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7DisableLSAInitialPCGFile`

Sets the PCG solver to use the default initial conditions.

**Syntax**

```c
long St7DisableLSAInitialPCGFile(long uID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetLSAInitialPCGFileState`

Returns the state assigned for the PCG initial conditions.

**Syntax**

```c
long St7GetLSAInitialPCGFileState(long uID, bool* State)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `State` — btTrue if the starting vector for the PCG solver is obtained from the initial conditions file.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetLSAInitialPCGFile`

Assigns the initial conditions file used by the PCG solver.

**Syntax**

```c
long St7SetLSAInitialPCGFile(long uID, char* FileName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
