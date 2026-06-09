---
title: "Animation"
source: "Strand7 R246 API Manual"
pages: 97–101
---

# Animation

Import/Export Utilities

[ipANSYSExportNonlinearMat] - Export nonlinear material data, either
btTrue or btFalse.

[ipANSYSExportHeatTransfer] - Export heat transfer property data,
either btTrue or btFalse.

[ipANSYSExportPreLoadNSMass] - Export pre-load and non-structural
mass attributes.

[ipANSYSExportTetraOption] - Export Tet4/Tet10 brick elements as
SOLID72/SOLID92.

Mode
Controls the display of a progress bar, either ieQuietRun or ieProgressRun.
Errors

ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CannotWriteExportFile, ERR7_FileNotOpen,
ERR7_InvalidAnsysEndReleaseOption,
ERR7_InvalidAnsysExportFormat, ERR7_InvalidAnsysExportUnits,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidImportExportMode, ERR7_InvalidLoadCase,
ERR7_NoError, ERR7_ResultFileIsOpen


---

### `St7PlayAnimationFile`

Opens and plays a SAF animation file in an animation window.

**Syntax**

```c
long St7PlayAnimationFile(long pHandle, char* FileName,
long* aHandle)
```

**Input Parameters**

- `pHandle` — The Windows handle for the parent control or form. Passing a 0 value results in a free-floating animation window.
- `FileName` — Full path and name for the SAF animation file.

**Output Parameters**

- `aHandle` — The Windows handle for the animation window.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CannotSetWindowParent, ERR7_FileNotFound,
ERR7_InvalidAnimationFile, ERR7_NoError,
ERR7_TooManyAnimations
```


---

### `St7CreateAnimation`

Creates a SAF animation file and plays it in an animation window. The Strand7
model referenced by uID must have a results file open.

**Syntax**

```c
long St7CreateAnimation(long uID, long* Integers, long*
aHandle)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Integers[0..4]` — [ipAniParentHandle] - The Windows handle for the parent control or form. Passing a 0 value results in a free-floating animation window. [ipAniCase] - The result case index for a single case animation. [ipNumFrames] - The number of animation frames for a single case animation. For a multi case animation, passing a -1 value will animate all result cases, passing a 0 value will animate only those cases marked using the St7SetAnimationCase function. [ipAniWidth] - The width in pixels for the animation window. [ipAniHeight] - The height in pixels for the animation window.

**Output Parameters**

- `aHandle` — The Windows handle for the animation window.

**Errors**

```
ERR7_AnimationDimensionsTooLarge,
ERR7_AnimationDimensionsTooSmall, ERR7_APINotInitialised,
ERR7_APINotLicensed, ERR7_CannotFindStubFile,
ERR7_CannotSetWindowParent, ERR7_CantDoWithModalWindows,
ERR7_CouldNotCreateModelWindow,
ERR7_CouldNotSaveAnimationFile, ERR7_ExceededResultCase,
ERR7_FileNotOpen, ERR7_InsufficientFrames,
ERR7_InvalidAnimationMode, ERR7_InvalidAnimationType,
ERR7_InvalidFileUnit, ERR7_ModelWindowWasNotCreated,
ERR7_ModelWindowWasNotShowing, ERR7_NoError,
ERR7_ReducedAnimation, ERR7_ResultFileNotOpen,
ERR7_TooManyAnimations
```


---

### `St7CreateAnimationFile`

Creates an animation file but does not play it.

**Syntax**

```c
long St7CreateAnimationFile(long uID, long* Integers, char*
FileName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Integers[0..5]` — [ipAniParentHandle] - The Windows handle for the parent control or form. Passing a 0 value results in a free-floating animation window. [ipAniCase] - The result case index for a single case animation. [ipNumFrames] - The number of animation frames for a single case animation. For a multi case animation, passing a -1 value will animate all result cases, passing a 0 value will animate only those cases marked using the St7SetAnimationCase function. [ipAniWidth] - The width in pixels for the animation window. [ipAniHeight] - The height in pixels for the animation window. [ipAniType] - The animation file type, one of kAniSAF, kAniEXE or kAniAVI.
- `FileName` — Full path and name for the animation file.

**Errors**

```
ERR7_AnimationDimensionsTooLarge,
ERR7_AnimationDimensionsTooSmall, ERR7_APINotInitialised,
ERR7_APINotLicensed, ERR7_CannotFindStubFile,
ERR7_CannotSetWindowParent, ERR7_CantDoWithModalWindows,
ERR7_CouldNotCreateModelWindow,
ERR7_CouldNotSaveAnimationFile, ERR7_ExceededResultCase,
ERR7_FileNotOpen, ERR7_InsufficientFrames,
ERR7_InvalidAnimationMode, ERR7_InvalidAnimationType,
ERR7_InvalidFileUnit, ERR7_ModelWindowWasNotCreated,
ERR7_ModelWindowWasNotShowing, ERR7_NoError,
ERR7_ReducedAnimation, ERR7_ResultFileNotOpen,
ERR7_TooManyAnimations
```


---

### `St7CloseAnimation`

Closes a SAF animation that is currently running.

**Syntax**

```c
long St7CloseAnimation(long aHandle)
```

**Input Parameters**

- `aHandle` — The Windows handle for the animation window.

**Errors**

```
ERR7_AnimationHandleOutOfRange, ERR7_AnimationNotRunning,
ERR7_APINotInitialised, ERR7_APINotLicensed, ERR7_NoError
```


---

### `St7SetAnimationCase`

Sets the state of a specified result case for multi-case animations.

**Syntax**

```c
long St7SetAnimationCase(long uID, long CaseNum, bool
Activate)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — Result case number.
- `Activate` — btTrue if the case is included in the animation.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_ExceededResultCase, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileNotOpen
```
