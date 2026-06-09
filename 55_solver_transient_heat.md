---
title: "Solver – Transient Heat"
source: "Strand7 R246 API Manual"
pages: 804–806
---

# Solver – Transient Heat

Errors

ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadCase, ERR7_NoError, ERR7_ResultFileIsOpen


---

### `St7GetHeatLoadCaseState`

Returns the state of the specified load case for Steady State heat analysis.

**Syntax**

```c
long St7GetHeatLoadCaseState(long uID, long CaseNum, bool*
State)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — Load case number.

**Output Parameters**

- `State` — btTrue if the specified load case is enabled for Steady State heat analysis.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadCase, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SetTHAInitialFile`

Assigns the initial conditions file used for Transient Heat analysis.

**Syntax**

```c
long St7SetTHAInitialFile(long uID, char* FileName, long
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

### `St7GetTHAInitialFile`

Returns the initial conditions file assigned for Transient Heat analysis.

**Syntax**

```c
long St7GetTHAInitialFile(long uID, char* FileName, long*
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

### `St7SetTHATemperatureLoadCase`

Assigns the load case to be used to specify the nodal temperature distribution
within the model when performing Transient Heat analysis.

**Syntax**

```c
long St7SetTHATemperatureLoadCase(long uID, long CaseNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — Load case number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadCase, ERR7_NoError, ERR7_ResultFileIsOpen
```
