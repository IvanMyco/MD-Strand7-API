---
title: "Solver – Harmonic Spectral and Linear Transient"
source: "Strand7 R246 API Manual"
pages: 810–814
---

# Solver – Harmonic Spectral and Linear Transient

Input Parameters

uID
Strand7 model file ID number.
Output Parameters

rType
Modal reaction type, either mrElementForce or mrInertiaForce.
Errors

ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError


## Solver – Harmonic, Spectral and Linear Transient


Solver – Harmonic, Spectral and Linear Transient


---

### `St7SetModalSuperpositionFile`

Assigns the modal superposition file used for Harmonic Response, Spectral
Response and Linear Transient analysis.

**Syntax**

```c
long St7SetModalSuperpositionFile(long uID, char* FileName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FileName` — Full path and name for the modal superposition file.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidModalFile, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetModalSuperpositionFile`

Returns the modal superposition file assigned for Harmonic Response, Spectral
Response and Linear Transient analysis.

**Syntax**

```c
long St7GetModalSuperpositionFile(long uID, char* FileName,
long MaxStringLen)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `MaxStringLen` — Maximum number of characters allocated for FileName.

**Output Parameters**

- `FileName` — Full path and name for the modal superposition file.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7GetNumModesInModalFile`

Returns the number of modes included in the modal superposition file assigned
for Harmonic Response, Spectral Response and Linear Transient analysis.

**Syntax**

```c
long St7GetNumModesInModalFile(long uID, long* NumModes)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `NumModes` — Number of modes in file.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidModalFile, ERR7_NoError
```


---

### `St7EnableMode`

Enables the specified mode in the modal superposition file for Harmonic
Response, Spectral Response and Linear Transient analysis.

**Syntax**

```c
long St7EnableMode(long uID, long ModeNum)


Solver – Harmonic, Spectral and Linear Transient
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `ModeNum` — Mode number to enable.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidModeNumber, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7DisableMode`

Disables the specified mode in the modal superposition file for Harmonic
Response, Spectral Response and Linear Transient analysis.

**Syntax**

```c
long St7DisableMode(long uID, long ModeNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `ModeNum` — Mode number to disable.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidModeNumber, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SetModeDampingRatio`

Sets the modal damping ratio for the specified mode in the modal superposition
file. This value is used for Harmonic Response, Spectral Response and Linear
Transient analysis.

**Syntax**

```c
long St7SetModeDampingRatio(long uID, long ModeNum, double
Ratio)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `ModeNum` — Mode number.
- `Ratio` — Modal damping ratio.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidModeNumber, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetModeDampingRatio`

Returns the modal damping ratio assigned for the specified mode in the modal
superposition file. This value is used for Harmonic Response, Spectral Response
and Linear Transient analysis.

**Syntax**

```c
long St7GetModeDampingRatio(long uID, long ModeNum, double*
Ratio)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `ModeNum` — Mode number.

**Output Parameters**

- `Ratio` — Modal damping ratio.
