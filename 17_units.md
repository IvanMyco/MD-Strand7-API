---
title: "Units"
source: "Strand7 R246 API Manual"
pages: 158–161
---

# Units

Syntax

long St7GetStageGroupState(long uID, long Stage, long
GroupID, bool* State)
Input Parameters

uID
Strand7 model file ID number.

Stage
The index of the specified stage.

GroupID
The ID number for the specified group.
Output Parameters

State
btTrue indicates that the specified group is enabled for the given stage.
Errors

ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_GroupIdDoesNotExist,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_StageDoesNotExist


---

### `St7SetUnits`

Sets the units system for a specified Strand7 model.

**Syntax**

```c
long St7SetUnits(long uID, long* Units)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Units[0..kLastUnit-1]` — [ipLENGTHU] - luMETRE, luCENTIMETRE, luMILLIMETRE, luFOOT or luINCH. [ipFORCEU] - fuNEWTON, fuKILONEWTON, fuMEGANEWTON, fuKILOFORCE, fuPOUNDFORCE, fuTONNEFORCE or fuKIPFORCE. [ipSTRESSU] - suPASCAL, suKILOPASCAL, suMEGAPASCAL, suKSCm, suPSI, suKSI or suPSF. [ipMASSU] - muKILOGRAM, muTONNE, muGRAM, muPOUND or muSLUG. [ipTEMPERU] - tuCELSIUS, tuFAHRENHEIT or tuKELVIN. [ipENERGYU] - euJOULE, euBTU, euFTLBF or euCALORIE.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_InvalidUnits,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetUnits`

Returns the units system for a specified Strand7 model.

**Syntax**

```c
long St7GetUnits(long uID, long* Units)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `Units[0..kLastUnit-1]` — [ipLENGTHU] - luMETRE, luCENTIMETRE, luMILLIMETRE, luFOOT or luINCH. [ipFORCEU] - fuNEWTON, fuKILONEWTON, fuMEGANEWTON, fuKILOFORCE, fuPOUNDFORCE, fuTONNEFORCE or fuKIPFORCE. [ipSTRESSU] - suPASCAL, suKILOPASCAL, suMEGAPASCAL, suKSCm, suPSI, suKSI or suPSF. [ipMASSU] - muKILOGRAM, muTONNE, muGRAM, muPOUND or muSLUG. [ipTEMPERU] - tuCELSIUS, tuFAHRENHEIT or tuKELVIN. [ipENERGYU] - euJOULE, euBTU, euFTLBF or euCALORIE.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetRCUnits`

Sets the units used for Plate RC results (in Results Settings). Note that this setting is
ignored unless St7EnableModelRCUnit is called.

**Syntax**

```c
long St7SetRCUnits(long uID, long AreaUnit, long
LengthUnit)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `AreaUnit` — Units of area in unit length squared; one of luMETRE, luCENTIMETRE, luMILLIMETRE, luFOOT or luINCH.
- `LengthUnit` — Units of length; one of luMETRE, luCENTIMETRE, luMILLIMETRE, luFOOT or luINCH.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_InvalidUnits,
ERR7_NoError
```


---

### `St7GetRCUnits`

Returns the units used for Plate RC results (in Results Settings). Note that this setting
is ignored unless St7EnableModelRCUnit is called.

**Syntax**

```c
long St7GetRCUnits(long uID, long* AreaUnit, long*
LengthUnit)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `AreaUnit` — Units of area in unit length squared; one of luMETRE, luCENTIMETRE, luMILLIMETRE, luFOOT or luINCH.
- `LengthUnit` — Units of length; one of luMETRE, luCENTIMETRE, luMILLIMETRE, luFOOT or luINCH.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7ConvertUnits`

Converts the current model into the specified units system.
