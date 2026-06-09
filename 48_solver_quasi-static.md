---
title: "Solver – Quasi-Static"
source: "Strand7 R246 API Manual"
pages: 765–766
---

# Solver – Quasi-Static

Solver – Nonlinear Static
Strand7 model file ID number.

MaxStringLen
Maximum number of characters allocated for FileName.
Output Parameters

FileName
Full path and name for the initial conditions file.

CaseNum
Result case number within FileName to be used as the initial conditions.
Errors

ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError


---

### `St7SetQSAInitialFile`

Assigns the initial conditions file used by the Quasi-Static solver.

**Syntax**

```c
long St7SetQSAInitialFile(long uID, char* FileName, long
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

### `St7GetQSAInitialFile`

Returns the initial conditions file assigned for Quasi-Static analysis.

**Syntax**

```c
long St7GetQSAInitialFile(long uID, char* FileName, long*
CaseNum, long MaxStringLen)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
