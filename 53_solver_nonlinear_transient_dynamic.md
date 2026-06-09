---
title: "Solver – Nonlinear Transient Dynamic"
source: "Strand7 R246 API Manual"
pages: 797–801
---

# Solver – Nonlinear Transient Dynamic

Solver – Linear Transient Dynamic


---

### `St7GetLTASolutionType`

Returns the solution type option assigned for Linear Transient analysis.

**Syntax**

```c
long St7GetLTASolutionType(long uID, long* SolutionType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `SolutionType` — Solution type, either stFullSystem or stSuperposition.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLTASolutionType, ERR7_NoError
```


---

### `St7SetNTAInitialFile`

Assigns the initial conditions file used for Nonlinear Transient analysis.

**Syntax**

```c
long St7SetNTAInitialFile(long uID, char* FileName, long
CaseNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FileName` — Full path and name for the initial conditions file.
- `CaseNum` — Result case number within FileName to be used as the initial conditions.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidInitialCaseNumber, ERR7_InvalidInitialFile,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetNTAInitialFile`

Returns the initial conditions file assigned for Nonlinear Transient analysis.

**Syntax**

```c
long St7GetNTAInitialFile(long uID, char* FileName, long*
CaseNum, long MaxStringLen)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `MaxStringLen` — Maximum number of characters allocated for FileName

**Output Parameters**

- `FileName` — Full path and name for the initial conditions file.
- `CaseNum` — Result case number within FileName to be used as the initial conditions.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetNTALoadPositionTable`

Assigns a Factor vs Position table for the specified Nonlinear Transient analysis
load case.

**Syntax**

```c
long St7SetNTALoadPositionTable(long uID, long CaseNum,
long TableNum, long UCSId, long Axis)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — Load case number.
- `TableNum` — ID number for the Factor vs Position table, zero for none.
- `UCSId` — UCS ID number used when evaluating position data.
- `Axis` — Local UCS axis, one of 1, 2 or 3.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadCase, ERR7_InvalidPositionTableAxis,
ERR7_InvalidTableType, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_TableDoesNotExist
```


---

### `St7GetNTALoadPositionTable`

Returns the Factor vs Position table associated with the specified Nonlinear
Transient load case.

**Syntax**

```c
long St7GetNTALoadPositionTable(long uID, long CaseNum,
long* TableNum, long* UCSId, long* Axis)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — Load case number.

**Output Parameters**

- `TableNum` — ID number for the Factor vs Position table, zero for none.
- `UCSId` — UCS ID number used when evaluating position data.
- `Axis` — Local UCS axis, one of 1, 2 or 3.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadCase, ERR7_NoError
```


---

### `St7SetNTAFreedomPositionTable`

Assigns a Factor vs Position table for the specified Nonlinear Transient freedom
case.

**Syntax**

```c
long St7SetNTAFreedomPositionTable(long uID, long CaseNum,
long TableNum, long UCSId, long Axis)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — Freedom case number.
- `TableNum` — ID number for the Factor vs Position table, zero for none.
- `UCSId` — UCS ID number used when evaluating position data.
- `Axis` — Local UCS axis, one of 1, 2 or 3.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidPositionTableAxis,
ERR7_InvalidTableType, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_TableDoesNotExist
```


---

### `St7GetNTAFreedomPositionTable`

Returns the Factor vs Position table associated with the specified Nonlinear
Transient freedom case.
