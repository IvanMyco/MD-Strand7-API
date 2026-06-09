---
title: "Attributes General"
source: "Strand7 R246 API Manual"
pages: 496–501
---

# Attributes General

ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen


---

### `St7SetElementProperty`

Sets the property for the specified element. The property does not need to be
created in advance.

**Syntax**

```c
long St7SetElementProperty(long uID, long Entity, long
EltNum, long PropNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Entity` — Strand7 element type, one of tyBEAM, tyPLATE or tyBRICK.
- `EltNum` — Element number.
- `PropNum` — Property number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntity, ERR7_InvalidFileUnit,
ERR7_NoError, ERR7_ResultFileIsOpen, ERR7_UnknownError
```


---

### `St7GetElementProperty`

Returns the property assigned to the specified element.

**Syntax**

```c
long St7GetElementProperty(long uID, long Entity, long
EltNum, long* PropNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Entity` — Strand7 element type, one of tyBEAM, tyPLATE or tyBRICK.
- `EltNum` — Element number.

**Output Parameters**

- `PropNum` — Property number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_ExceededTotal, ERR7_FileNotOpen,
ERR7_InvalidEntity, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetElementPropertySwitch`

Specifies a property switch for a staged analysis.

**Syntax**

```c
long St7SetElementPropertySwitch(long uID, long Entity,
long EltNum, long PropID, long StageID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Entity` — Strand7 element type, one of tyBEAM, tyPLATE or tyBRICK.
- `EltNum` — Element number.
- `PropID` — Property number.
- `StageID` — Stage ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidPropertyNumber, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_StageDoesNotExist,
ERR7_UnknownError
```


---

### `St7GetElementPropertySequence`

Returns the property sequence assigned to a specified element for staged
analysis. The St7GetNumStages function can be used to determine the number of
stages in the model.

**Syntax**

```c
long St7GetElementPropertySequence(long uID, long Entity,
long EltNum, long MaxPoints, long* Props, long*
Stages)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Entity` — Strand7 element type, one of tyBEAM, tyPLATE or tyBRICK.
- `EltNum` — Element number.
- `MaxPoints` — Maximum amount of storage allocated for the Props and Stages arrays.

**Output Parameters**

- `Props[0..MaxPoints-1]` — An array containing the property number assigned at each stage of the analysis.
- `Stages[0..MaxPoints-1]` — An array containing the stage ID number assigned at each stage of the analysis.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_NoError, ERR7_StageDoesNotExist, ERR7_UnknownError
```


---

### `St7DeleteAttribute`

Deletes the specified attribute, see Attribute Types for further information.

**Syntax**

```c
long St7DeleteAttribute(long uID, long Entity, long
EntityNum, long AttributeOrd, long* Integers)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Entity` — Entity type, one of tyNODE, tyBEAM, tyPLATE, tyBRICK, tyVERTEX, tyGEOMETRYEDGE, tyGEOMETRYFACE or tyLOADPATH.
- `EntityNum` — Entity number.
- `AttributeOrd` — Attribute identifier, see Attribute Types for additional information.
- `Integers[0..2]` — [0] - Local attribute number, see Attribute Types for additional information. [1] - Attribute load/freedom case number, see Attribute Types for additional information. [2] - Attribute ID number, see Attribute Types for additional information.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SetEntityGroup`

Assigns the specified entity to a given group.

**Syntax**

```c
long St7SetEntityGroup(long uID, long Entity, long
EntityNum, long GroupID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Entity` — Strand7 entity type, one of tyBEAM, tyPLATE, tyBRICK, tyLINK, tyGEOMETRYFACE or tyLOADPATH.
- `EntityNum` — Entity number.
- `GroupID` — Group ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidEntity,
ERR7_InvalidFileUnit, ERR7_InvalidLoadPathID, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_UnknownError
```
