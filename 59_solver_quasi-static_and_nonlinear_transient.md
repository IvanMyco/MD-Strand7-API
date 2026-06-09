---
title: "Solver – Quasi-Static and Nonlinear Transient"
source: "Strand7 R246 API Manual"
pages: 829–830
---

# Solver – Quasi-Static and Nonlinear Transient

Solver – Linear and Nonlinear Transient Dynamic
Errors

ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen


Solver – Quasi-Static and Nonlinear Transient Dynamic


---

### `St7SetTransientTemperatureInputType`

Sets the type of temperature data used for Quasi-Static and Nonlinear Transient
analysis.

**Syntax**

```c
long St7SetTransientTemperatureInputType(long uID, long
InputType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `InputType` — Temperature type, either ttFromFile or ttNodalTemp.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidTransientTempType, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetTransientHeatFile`

Assigns the temperature file used for Quasi-Static and Nonlinear Transient analysis.

**Syntax**

```c
long St7SetTransientHeatFile(long uID, char* FileName,
double RefTemp)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
  FileName
