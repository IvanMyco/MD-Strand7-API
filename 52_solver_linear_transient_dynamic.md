---
title: "Solver – Linear Transient Dynamic"
source: "Strand7 R246 API Manual"
pages: 793–796
---

# Solver – Linear Transient Dynamic

Solver – Spectral Response
Errors

ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidSpectrumType, ERR7_NoError,
ERR7_ResultFileIsOpen


---

### `St7SetSRAResultsSign`

Sets the results sign option for the Spectral Response solver.

**Syntax**

```c
long St7SetSRAResultsSign(long uID, long ResultsSign)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `ResultsSign` — Results sign, either rsAuto or rsAbsolute.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidResultsSign, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetLTAInitialFile`

Assigns the initial conditions file used for Linear Transient analysis.

**Syntax**

```c
long St7SetLTAInitialFile(long uID, char* FileName, long
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

### `St7GetLTAInitialFile`

Returns the initial conditions file assigned for Linear Transient analysis.

**Syntax**

```c
long St7GetLTAInitialFile(long uID, char* FileName, long*
CaseNum, long MaxStringLen)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `MaxStringLen` — Maximum number of characters allocated for FileName.

**Output Parameters**

- `FileName` — Full path and name for the initial conditions file.
- `CaseNum` — Result case number within FileName to be used as the initial conditions.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetLTAMethod`

Sets the integration method used for Linear Transient analysis.

**Syntax**

```c
long St7SetLTAMethod(long uID, long Method)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Method` — Time integration method, either ltWilson or ltNewmark.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLTAMethod, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetLTAMethod`

Returns the integration method assigned for Linear Transient analysis.

**Syntax**

```c
long St7GetLTAMethod(long uID, long* Method)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `Method` — Time integration method, either ltWilson or ltNewmark.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetLTASolutionType`

Sets the solution type option for Linear Transient analysis.

**Syntax**

```c
long St7SetLTASolutionType(long uID, long SolutionType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `SolutionType` — Solution type, either stFullSystem or stSuperposition.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLTASolutionType, ERR7_NoError,
ERR7_ResultFileIsOpen
```
