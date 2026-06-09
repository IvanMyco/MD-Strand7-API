---
title: "Solver – Nonlinear Static"
source: "Strand7 R246 API Manual"
pages: 750–764
---

# Solver – Nonlinear Static

Errors

ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase, ERR7_NoError,
ERR7_ResultFileIsOpen


---

### `St7SetNLAStagedAnalysis`

Sets the state of the staged analysis option for the Nonlinear Static solver.

**Syntax**

```c
long St7SetNLAStagedAnalysis(long uID, bool StagedAnalysis)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `StagedAnalysis` — btTrue to perform staged analysis.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetNLAStagedAnalysis`

Returns the state of the staged analysis option for the Nonlinear Static solver.

**Syntax**

```c
long St7GetNLAStagedAnalysis(long uID, bool*
StagedAnalysis)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `StagedAnalysis` — btTrue to perform staged nonlinear static analysis.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7EnableNLAStage`

Activates the specified stage such that it is included when performing Nonlinear
Static analysis.

**Syntax**

```c
long St7EnableNLAStage(long uID, long Stage)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Stage` — Stage number to be enabled.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_StageDoesNotExist
```


---

### `St7DisableNLAStage`

Deactivates the specified stage such that it is not included when performing
Nonlinear Static analysis.

**Syntax**

```c
long St7DisableNLAStage(long uID, long Stage)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Stage` — Stage number to be disabled.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_StageDoesNotExist
```


---

### `St7GetNLAStageState`

Returns the state assigned to the specified stage for Nonlinear Static analysis.

**Syntax**

```c
long St7GetNLAStageState(long uID, long Stage, bool* State)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Stage` — Stage number.

**Output Parameters**

- `State` — btTrue if the specified stage is enabled.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_NoError, ERR7_StageDoesNotExist
```


---

### `St7AddNLAIncrement`

Adds a new blank increment to the Nonlinear Static analysis load increment
table.

**Syntax**

```c
long St7AddNLAIncrement(long uID, long Stage, char*
IncName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Stage` — Stage number - use zero for unstaged analysis.
- `IncName` — String containing the increment name.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_StageDoesNotExist
```


---

### `St7InsertNLAIncrement`

Inserts a new blank increment at the specified position in the Nonlinear Static
analysis load increment table.

**Syntax**

```c
long St7InsertNLAIncrement(long uID, long Stage, long
Increment, char* IncName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Stage` — Stage number - use zero for unstaged analysis.
- `Increment` — Increment number.
- `IncName` — String containing the increment name.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_IncrementDoesNotExist,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileIsOpen,
ERR7_StageDoesNotExist
```


---

### `St7DeleteNLAIncrement`

Deletes the specified increment from the Nonlinear Static analysis load increment
table.

**Syntax**

```c
long St7DeleteNLAIncrement(long uID, long Stage, long
Increment)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Stage` — Stage number - use zero for unstaged analysis.
- `Increment` — Increment number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_IncrementDoesNotExist,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileIsOpen,
ERR7_StageDoesNotExist
```


---

### `St7GetNumNLAIncrements`

Returns the total number of increments assigned in the Nonlinear Static analysis
load increment table.

**Syntax**

```c
long St7GetNumNLAIncrements(long uID, long Stage, long*
NumIncrements)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Stage` — Stage number - use zero for unstaged analysis.

**Output Parameters**

- `NumIncrements` — Total number of increments.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_StageDoesNotExist
```


---

### `St7SetNLALoadIncrementFactor`

Assigns the load case factors for the specified increment in the Nonlinear Static
analysis load increment table.

**Syntax**

```c
long St7SetNLALoadIncrementFactor(long uID, long Stage,
long Increment, long CaseNum, double dFactor)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Stage` — Stage number - use zero for unstaged analysis.
- `Increment` — Increment number.
- `CaseNum` — Load case number.
- `dFactor` — Load case factor.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_IncrementDoesNotExist,
ERR7_InvalidFileUnit, ERR7_InvalidLoadCase, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_StageDoesNotExist
```


---

### `St7GetNLALoadIncrementFactor`

Returns the load case factors assigned for the specified increment in the
Nonlinear Static analysis load increment table.

**Syntax**

```c
long St7GetNLALoadIncrementFactor(long uID, long Stage,
long Increment, long CaseNum, double* dFactor)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Stage` — Stage number - use zero for unstaged analysis.
- `Increment` — Increment number.
- `CaseNum` — Load case number.

**Output Parameters**

- `dFactor` — Load case factor.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_IncrementDoesNotExist,
ERR7_InvalidFileUnit, ERR7_InvalidLoadCase, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_StageDoesNotExist
```


---

### `St7SetNLAFreedomIncrementFactor`

Assigns the freedom case factors for the specified increment in the Nonlinear
Static analysis load increment table.

**Syntax**

```c
long St7SetNLAFreedomIncrementFactor(long uID, long Stage,
long Increment, long CaseNum, double dFactor)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Stage` — Stage number - use zero for unstaged analysis.
- `Increment` — Increment number.
- `CaseNum` — Freedom case number.
- `dFactor` — Freedom case factor.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_IncrementDoesNotExist,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_StageDoesNotExist
```


---

### `St7GetNLAFreedomIncrementFactor`

Returns the freedom case factors assigned in the specified increment in the
Nonlinear Static analysis load increment table.

**Syntax**

```c
long St7GetNLAFreedomIncrementFactor(long uID, long Stage,
long Increment, long CaseNum, double* dFactor)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Stage` — Stage number - use zero for unstaged analysis.
- `Increment` — Increment number.
- `CaseNum` — Freedom case number.

**Output Parameters**

- `dFactor` — Freedom case factor.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_IncrementDoesNotExist,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_StageDoesNotExist
```


---

### `St7EnableNLALoadCase`

Activates the specified load case such that it is included in Nonlinear Static
analysis.

**Syntax**

```c
long St7EnableNLALoadCase(long uID, long Stage, long
CaseNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Stage` — Stage number - use zero for unstaged analysis.
- `CaseNum` — Load case number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_IncrementDoesNotExist,
ERR7_InvalidFileUnit, ERR7_InvalidLoadCase, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_StageDoesNotExist
```


---

### `St7DisableNLALoadCase`

Deactivates the specified load case such that it is not included in Nonlinear Static
analysis.

**Syntax**

```c
long St7DisableNLALoadCase(long uID, long Stage, long
CaseNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Stage` — Stage number - use zero for unstaged analysis.
- `CaseNum` — Load case number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_IncrementDoesNotExist,
ERR7_InvalidFileUnit, ERR7_InvalidLoadCase, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_StageDoesNotExist
```


---

### `St7GetNLALoadCaseState`

Returns the state assigned to the specified load case for Nonlinear Static analysis.

**Syntax**

```c
long St7GetNLALoadCaseState(long uID, long Stage, long
CaseNum, bool* State)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Stage` — Stage number - use zero for unstaged analysis.
- `CaseNum` — Load case number.

**Output Parameters**

- `State` — btTrue if the specified load case is enabled for Nonlinear Static analysis.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_IncrementDoesNotExist,
ERR7_InvalidFileUnit, ERR7_InvalidLoadCase, ERR7_NoError,
ERR7_StageDoesNotExist
```


---

### `St7EnableNLAFreedomCase`

Enables the specified freedom case such that it is included in Nonlinear Static
analysis.

**Syntax**

```c
long St7EnableNLAFreedomCase(long uID, long Stage, long
CaseNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Stage` — Stage number - use zero for unstaged analysis.
- `CaseNum` — Freedom case number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_IncrementDoesNotExist,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_StageDoesNotExist
```


---

### `St7DisableNLAFreedomCase`

Deactivates the specified freedom case such that it is not included in Nonlinear
Static analysis.

**Syntax**

```c
long St7DisableNLAFreedomCase(long uID, long Stage, long
CaseNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Stage` — Stage number - use zero for unstaged analysis.
- `CaseNum` — Freedom case number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_IncrementDoesNotExist,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_StageDoesNotExist
```


---

### `St7GetNLAFreedomCaseState`

Returns the state assigned to the specified freedom case for Nonlinear Static
analysis.

**Syntax**

```c
long St7GetNLAFreedomCaseState(long uID, long Stage, long
CaseNum, bool* State)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Stage` — Stage number - use zero for unstaged analysis.
- `CaseNum` — Freedom case number.

**Output Parameters**

- `State` — btTrue if the specified freedom case is enabled for Nonlinear Static analysis.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_IncrementDoesNotExist,


ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase, ERR7_NoError,
ERR7_StageDoesNotExist
```


---

### `St7SetNLAInitialFile`

Assigns the initial conditions file used for Nonlinear Static analysis.

**Syntax**

```c
long St7SetNLAInitialFile(long uID, char* FileName, long
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

### `St7GetNLAInitialFile`

Returns the initial conditions file assigned for Nonlinear Static analysis.

**Syntax**

```c
long St7GetNLAInitialFile(long uID, char* FileName, long*
CaseNum, long MaxStringLen)
```

**Input Parameters**

  uID
