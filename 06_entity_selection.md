---
title: "Entity Selection"
source: "Strand7 R246 API Manual"
pages: 47–48
---

# Entity Selection

Utility
Syntax

long St7EnableModelRCUnit(long uID)
Input Parameters

uID
Strand7 model file ID number.
Errors

ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError


---

### `St7DisableModelRCUnit`

Restores the API default report of plate RC results in consistent model units,
overriding the length and area units set by St7SetRCUnits.

**Syntax**

```c
long St7DisableModelRCUnit(long uID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetEntitySelectState`

Sets the selected state of a specified entity.

**Syntax**

```c
long St7SetEntitySelectState(long uID, long Entity, long
EntityNum, long EndEdgeFace, bool Selected)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Entity` — Entity type, one of tyNODE, tyBEAM, tyPLATE, tyBRICK, tyLINK, tyVERTEX, tyGEOMETRYEDGE, tyGEOMETRYFACE or tyLOADPATH.
- `EntityNum` — Entity number.
- `EndEdgeFace` — Local entity number, either 1 or 2 for tyBEAM, one of 1,2,3 or 4 for tyPLATE or 1,2,3,4,5 or 6 for tyBRICK. Use zero to select tyNODE and for entire tyBEAM, tyPLATE and tyBRICK.
- `Selected` — Selected state, either btTrue or btFalse.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidSelectionEndEdgeFace, ERR7_NoError
```
