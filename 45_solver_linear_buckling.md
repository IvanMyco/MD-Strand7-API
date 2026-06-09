---
title: "Solver – Linear Buckling"
source: "Strand7 R246 API Manual"
pages: 743–746
---

# Solver – Linear Buckling

Solver – Linear Static

FileName
Full path and name for the initial conditions file for the PCG solver.
Errors

ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen


---

### `St7GetLSAInitialPCGFile`

Returns the initial conditions file assigned to the PCG solver.

**Syntax**

```c
long St7GetLSAInitialPCGFile(long uID, char* FileName, long
MaxStringLen)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `MaxStringLen` — Maximum number of characters allocated for FileName.

**Output Parameters**

- `FileName` — Full path and name for the initial conditions file for the PCG solver.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetLBAInitialFile`

Assigns the initial conditions file used by the Linear Buckling solver.

**Syntax**

```c
long St7SetLBAInitialFile(long uID, char* FileName, long
CaseNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FileName` — Full path and name for the initial conditions file for the Linear Buckling solver.
- `CaseNum` — Result case number within the initial conditions file used by the solver.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidInitialCaseNumber, ERR7_InvalidInitialFile,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetLBAInitialFile`

Returns the initial conditions file assigned to the Linear Buckling solver.

**Syntax**

```c
long St7GetLBAInitialFile(long uID, char* FileName, long*
CaseNum, long MaxStringLen)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `MaxStringLen` — Maximum number of characters allocated for FileName.

**Output Parameters**

- `FileName` — Full path and name for the initial conditions file used by the Linear Buckling solver.
- `CaseNum` — Result case number within the initial conditions file used by the solver.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetLBANumModes`

Sets the number of modes to be found when running the Linear Buckling solver.

**Syntax**

```c
long St7SetLBANumModes(long uID, long NumModes)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `NumModes` — Number of modes to be found.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidNumModes, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetLBANumModes`

Returns the number of modes to be found when running the Linear Buckling
solver.

**Syntax**

```c
long St7GetLBANumModes(long uID, long* NumModes)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `NumModes` — Number of modes to be found.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetLBAShift`

Sets the frequency shift used by the Linear Buckling solver. The first modes found
both above and below the shift value will be found when running the solver.

**Syntax**

```c
long St7SetLBAShift(long uID, double Shift)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Shift` — The eigenvalue shift to be applied when performing a Linear Buckling analysis. The first modes that occur on either side of this value are included in the analysis.
