---
title: "Solver – Harmonic and Spectral Response"
source: "Strand7 R246 API Manual"
pages: 807–809
---

# Solver – Harmonic and Spectral Response

Solver – Transient Heat


---

### `St7GetTHATemperatureLoadCase`

Returns the load case assigned to specify the nodal temperature distribution in
the model for Transient Heat analysis.

**Syntax**

```c
long St7GetTHATemperatureLoadCase(long uID, long* CaseNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `CaseNum` — Load case number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetModalLoadType`

Sets the modal load type used when performing Harmonic and Spectral
Response analysis.

**Syntax**

```c
long St7SetModalLoadType(long uID, long lType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `lType` — Modal load type, one of mtBaseAcc, mtBaseVel, mtBaseDisp or mtAppliedLoad.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidModalLoadType, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetModalLoadType`

Returns the modal load type assigned for Harmonic and Spectral Response
analysis.

**Syntax**

```c
long St7GetModalLoadType(long uID, long* lType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `lType` — Modal load type, one of mtBaseAcc, mtBaseVel, mtBaseDisp or mtAppliedLoad.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetModalNodeReactionType`

Sets the type of modal reaction calculation used for Harmonic and Spectral
Response analysis.

**Syntax**

```c
long St7SetModalNodeReactionType(long uID, long rType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `rType` — Modal reaction type, either mrElementForce or mrInertiaForce.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetModalNodeReactionType`

Returns the type of modal reaction calculation used for Harmonic and Spectral
Response analysis.

**Syntax**

```c
long St7GetModalNodeReactionType(long uID, long* rType)
```
