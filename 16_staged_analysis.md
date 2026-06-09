---
title: "Staged Analysis"
source: "Strand7 R246 API Manual"
pages: 150–157
---

# Staged Analysis

---

### `St7GetGroupColour`

Returns the colour of the specified group for entity display purposes.

**Syntax**

```c
long St7GetGroupColour(long uID, long GroupID, long*
GroupCol)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `GroupID` — The ID number of the specified group.

**Output Parameters**

- `GroupCol` — Group colour as a 32 bit RGB value.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_GroupIdDoesNotExist,
ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7AddStage`

Adds a new nonlinear analysis stage to a Strand7 model.

**Syntax**

```c
long St7AddStage(long uID, char* StageName, long* Integers)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `StageName` — String containing the name of the new stage.
- `Integers[0..2]` — [ipStageMorph] - Morphing option, either btTrue or btFalse. [ipStageMovedFixedNodes] - Move fixed nodes option, either btTrue or btFalse. [ipStageRotateClusters] - Rotate clusters option, either btTrue or btFalse.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_ExceededMaxNumStages, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7InsertStage`

Inserts a new nonlinear analysis stage in a Strand7 model.

**Syntax**

```c
long St7InsertStage(long uID, long Stage, char* StageName,
long* Integers)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Stage` — Index at which to insert the new stage.
- `StageName` — String containing the name of the new stage.
- `Integers[0..2]` — [ipStageMorph] - Morphing option, either btTrue or btFalse. [ipStageMovedFixedNodes] - Move fixed nodes option, either btTrue or btFalse. [ipStageRotateClusters] - Rotate clusters option, either btTrue or btFalse.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_StageDoesNotExist
```


---

### `St7DeleteStage`

Deletes a nonlinear analysis stage from a Strand7 model.

**Syntax**

```c
long St7DeleteStage(long uID, long Stage)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Stage` — Index of the stage to be deleted.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_StageDoesNotExist
```


---

### `St7GetNumStages`

Returns the number of nonlinear analysis stages in a Strand7 model.

**Syntax**

```c
long St7GetNumStages(long uID, long* NumStages)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `NumStages` — The number of stages in the model.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetStageName`

Sets the name of a specified nonlinear analysis stage.

**Syntax**

```c
long St7SetStageName(long uID, long Stage, char* StageName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Stage` — The index of the specified stage.
- `StageName` — String containing the new name of the stage.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_StageDoesNotExist
```


---

### `St7GetStageName`

Returns the name of a specified nonlinear analysis stage.

**Syntax**

```c
long St7GetStageName(long uID, long Stage, char* StageName,
long MaxStringLen)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Stage` — The index of the specified stage.
- `MaxStringLen` — The maximum number of characters allocated for StageName.

**Output Parameters**

- `StageName` — String containing the name of the specified stage.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_StageDoesNotExist
```


---

### `St7SetStageData`

Sets the data for a specified nonlinear analysis stage.

**Syntax**

```c
long St7SetStageData(long uID, long Stage, long* Integers)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Stage` — The index of the specified stage.
- `Integers[0..2]` — [ipStageMorph] - Morphing option, either btTrue or btFalse. [ipStageMovedFixedNodes] - Move fixed nodes option, either btTrue or btFalse. [ipStageRotateClusters] - Rotate clusters option, either btTrue or btFalse.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_StageDoesNotExist
```


---

### `St7GetStageData`

Returns the data for a specified nonlinear analysis stage.

**Syntax**

```c
long St7GetStageData(long uID, long Stage, long* Integers)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Stage` — The index of the specified stage.

**Output Parameters**

- `Integers[0..2]` — [ipStageMorph] - Morphing option, either btTrue or btFalse. [ipStageMovedFixedNodes] - Move fixed nodes option, either btTrue or btFalse. [ipStageRotateClusters] - Rotate clusters option, either btTrue or btFalse.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_StageDoesNotExist
```


---

### `St7EnableStageGroup`

Enables a specified group for a given nonlinear analysis stage. The elements in all
groups enabled for a given stage will participate in the solution once the
specified stage becomes active.

**Syntax**

```c
long St7EnableStageGroup(long uID, long Stage, long
GroupID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Stage` — The index of the specified stage.
- `GroupID` — The ID number for the group to be enabled for the specified stage.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_GroupIdDoesNotExist,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileIsOpen,
ERR7_StageDoesNotExist
```


---

### `St7DisableStageGroup`

Disables a specified group for a given nonlinear analysis stage. The elements in all
groups enabled for a given stage will participate in the solution once the
specified stage becomes active.

**Syntax**

```c
long St7DisableStageGroup(long uID, long Stage, long
GroupID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Stage` — The index of the specified stage.
- `GroupID` — The ID number for the group to be disabled for the specified stage.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_GroupIdDoesNotExist,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileIsOpen,
ERR7_StageDoesNotExist
```


---

### `St7GetStageGroupState`

Returns whether a specified group is currently enabled for a given nonlinear
analysis stage.
