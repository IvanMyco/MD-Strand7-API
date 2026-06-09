---
title: "Solver – Load Influence"
source: "Strand7 R246 API Manual"
pages: 747–749
---

# Solver – Load Influence

Solver – Linear Buckling
Errors

ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen


---

### `St7GetLBAShift`

Returns the shift value assigned to the Linear Buckling solver. The first modes found
both above and below the shift value will be found when running the solver.

**Syntax**

```c
long St7GetLBAShift(long uID, double* Shift)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `Shift` — The eigenvalue shift to be applied when performing Linear Buckling analysis. The first modes that occur on either side of this value are included in the analysis.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7EnableLIALoadCase`

Activates the specified load and freedom case combination such that it is
included when performing Load Influence analysis.

**Syntax**

```c
long St7EnableLIALoadCase(long uID, long LCaseNum, long
FCaseNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LCaseNum` — Load case number.
- `FCaseNum` — Freedom case number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7DisableLIALoadCase`

Deactivates the specified load and freedom case combination such that it is not
included when performing Load Influence analysis.

**Syntax**

```c
long St7DisableLIALoadCase(long uID, long LCaseNum, long
FCaseNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LCaseNum` — Load case number.
- `FCaseNum` — Freedom case number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetLIALoadCaseState`

Returns the state assigned to the specified load and freedom case combination
for Load Influence analysis.

**Syntax**

```c
long St7GetLIALoadCaseState(long uID, long LCaseNum, long
FCaseNum, bool* State)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LCaseNum` — Load case number.
- `FCaseNum` — Freedom case number.

**Output Parameters**

- `State` — btTrue is the specified load and freedom case combination is enabled for Load Influence analysis.
