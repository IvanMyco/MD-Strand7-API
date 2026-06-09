---
title: "Solver – Steady-State Heat"
source: "Strand7 R246 API Manual"
pages: 802–803
---

# Solver – Steady-State Heat

Syntax

long St7GetNTAFreedomPositionTable(long uID, long CaseNum,
long* TableNum, long* UCSId, long* Axis)
Input Parameters

uID
Strand7 model file ID number.

CaseNum
Freedom case number.
Output Parameters

TableNum
ID number for the Factor vs Position table, zero for none.

UCSId
UCS ID number used when evaluating position data.

Axis
Local UCS axis, one of 1, 2 or 3.
Errors

ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_NoError


---

### `St7EnableHeatLoadCase`

Activates the specified load case such that is included when performing Steady
State heat analysis.

**Syntax**

```c
long St7EnableHeatLoadCase(long uID, long CaseNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — Load case number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadCase, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7DisableHeatLoadCase`

Deactivates the specified load case such that it is not included when performing
Steady State heat analysis.

**Syntax**

```c
long St7DisableHeatLoadCase(long uID, long CaseNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — Load case number.
