---
title: "Solver – Quasi-Static and Transient Dynamic"
source: "Strand7 R246 API Manual"
pages: 831–842
---

# Solver – Quasi-Static and Transient Dynamic

Solver – Quasi-Static and Nonlinear Transient Dynamic
Full path and name for the temperature file.

RefTemp
Reference temperature.
Errors

ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen


---

### `St7GetTransientHeatFile`

Returns the temperature file assigned for Quasi-Static and Nonlinear Transient
analysis.

**Syntax**

```c
long St7GetTransientHeatFile(long uID, char* FileName, long
MaxStringLen, double* RefTemp)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `MaxStringLen` — Maximum number of characters allocated for FileName.

**Output Parameters**

- `FileName` — Full path and name for the temperature file.
- `RefTemp` — Reference temperature.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7EnableTransientLoadCase`

Enables the specified load case for Quasi-Static and Transient analysis.

**Syntax**

```c
long St7EnableTransientLoadCase(long uID, long CaseNum)
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


---

### `St7DisableTransientLoadCase`

Disables the specified load case for Quasi-Static and Transient analysis.

**Syntax**

```c
long St7DisableTransientLoadCase(long uID, long CaseNum)
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


---

### `St7GetTransientLoadCaseState`

Returns the state of the specified load case for Quasi-Static and Transient analysis.

**Syntax**

```c
long St7GetTransientLoadCaseState(long uID, long CaseNum,
bool* State)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — Load case number.

**Output Parameters**

- `State` — btTrue if the specified load case is enabled.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadCase, ERR7_NoError
```


---

### `St7EnableTransientFreedomCase`

Enables the specified freedom case for Quasi-Static and Transient analysis.

**Syntax**

```c
long St7EnableTransientFreedomCase(long uID, long CaseNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — Freedom case number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7DisableTransientFreedomCase`

Disables the specified freedom case for Quasi-Static and Transient analysis.

**Syntax**

```c
long St7DisableTransientFreedomCase(long uID, long CaseNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — Freedom case number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetTransientFreedomCaseState`

Returns the state of the specified freedom case for Quasi-Static and Transient
analysis.

**Syntax**

```c
long St7GetTransientFreedomCaseState(long uID, long CaseNum,
bool* State)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — Freedom case number.

**Output Parameters**

- `State` — btTrue if the specified freedom case is enabled.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_NoError
```


---

### `St7SetTransientLoadTable`

Specifies the Factor vs Time table to be associated with a given load case for
Quasi-Static and Transient analysis.

**Syntax**

```c
long St7SetTransientLoadTable(long uID, long CaseNum, long
TableNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — Load case number.
- `TableNum` — Factor vs Time table ID, zero for none.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadCase, ERR7_NoError, ERR7_ResultFileIsOpen,
ERR7_TableDoesNotExist
```


---

### `St7GetTransientLoadTable`

Returns the Factor vs Time table associated with the specified load case for
Quasi-Static and Transient analysis.

**Syntax**

```c
long St7GetTransientLoadTable(long uID, long CaseNum, long*
TableNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — Load case number.

**Output Parameters**

- `TableNum` — Factor vs Time table ID, zero for none.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadCase, ERR7_NoError
```


---

### `St7SetTransientFreedomTable`

Specifies the Factor vs Time table to be associated with a given freedom case for
Quasi-Static and Transient analysis.

**Syntax**

```c
long St7SetTransientFreedomTable(long uID, long CaseNum,
long TableNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — Freedom case number.
- `TableNum` — Factor vs Time table ID, zero for none.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_TableDoesNotExist
```


---

### `St7GetTransientFreedomTable`

Returns the Factor vs Time table associated with the specified freedom case for
Quasi-Static and Transient analysis.

**Syntax**

```c
long St7GetTransientFreedomTable(long uID, long CaseNum,
long* TableNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — Freedom case number.

**Output Parameters**

- `TableNum` — Factor vs Time table ID, zero for none.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_NoError
```


---

### `St7SetNumTimeStepRows`

Sets the number of rows used to specify the integration intervals for Quasi-Static
and Transient analysis. Each row may have separate time step and integration
settings.

**Syntax**

```c
long St7SetNumTimeStepRows(long uID, long NumRows)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `NumRows` — Number of rows.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_ExceededMaxNumRows, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetNumTimeStepRows`

Returns the number of rows used to specify the integration interval for QuasiStatic and Transient analysis. Each row may have separate time step and
integration settings.

**Syntax**

```c
long St7GetNumTimeStepRows(long uID, long* NumRows)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `NumRows` — Number of rows.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetTimeStepData`

Sets the time step and integration data used for Quasi-Static and Transient
analysis. The integration data may be specified over multiple rows.

**Syntax**

```c
long St7SetTimeStepData(long uID, long Row, long NumSteps,
long SaveEvery, double TimeStep)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Row` — Integration data row.
- `NumSteps` — Total number of time steps in row.
- `SaveEvery` — Number of time steps between successive result cases.
- `TimeStep` — Time step size.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_InvalidTimeRow,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetTimeStepData`

Returns the time step and integration data used for Quasi-Static and Transient
analysis. The integration data may be specified over multiple rows.

**Syntax**

```c
long St7GetTimeStepData(long uID, long Row, long* NumSteps,
long* SaveEvery, double* TimeStep)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Row` — Integration data row.

**Output Parameters**

- `NumSteps` — Total number of time steps in row.
- `SaveEvery` — Number of time steps between successive result cases.
- `TimeStep` — Time step size.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_InvalidTimeRow,
ERR7_NoError
```


---

### `St7SetTimeStepUnit`

Sets the units for the time step used for Quasi-Static and Transient analysis.

**Syntax**

```c
long St7SetTimeStepUnit(long uID, long TimeUnit)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `TimeUnit` — Time-step units, one of tuMilliSec, tuSec, tuMin, tuHour, tuDay.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidTimeUnit, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetTimeStepUnit`

Returns the units assigned for the time step used for Quasi-Static and Transient
analysis.

**Syntax**

```c
long St7GetTimeStepUnit(long uID, long* TimeUnit)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `TimeUnit` — Time-step units, one of tuMilliSec, tuSec, tuMin, tuHour, tuDay.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7EnableMovingLoad`

Enables the specified moving load path for Quasi-Static and Transient analysis.

**Syntax**

```c
long St7EnableMovingLoad(long uID, long LoadPathID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LoadPathID` — Load path ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadPath, ERR7_InvalidLoadPathID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7DisableMovingLoad`

Disables the specified moving load path for Quasi-Static and Transient analysis.

**Syntax**

```c
long St7DisableMovingLoad(long uID, long LoadPathID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LoadPathID` — Load path ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadPath, ERR7_InvalidLoadPathID, ERR7_NoError,
ERR7_ResultFileIsOpen
```
