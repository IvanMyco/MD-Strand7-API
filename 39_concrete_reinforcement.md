---
title: "Concrete Reinforcement"
source: "Strand7 R246 API Manual"
pages: 638–645
---

# Concrete Reinforcement

---

### `St7DeleteLaminate`

Deletes the specified laminate.

**Syntax**

```c
long St7DeleteLaminate(long uID, long LamNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LamNum` — Laminate number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLaminateID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7DeleteUnusedLaminates`

Deletes all unused laminates in the specified model.

**Syntax**

```c
long St7DeleteUnusedLaminates(long uID, long* NumDeleted)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `NumDeleted` — Number of laminates deleted.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetTotalReinforcementLayouts`

Returns the total number and highest ID number of the concrete reinforcement
layouts in the specified model.

**Syntax**

```c
long St7GetTotalReinforcementLayouts(long uID, long*
NumLayouts, long* LastLayout)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `NumLayouts` — The total number of layouts in the model.
- `LastLayout` — The highest layout ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7GetReinforcementLayoutNumByIndex`

Returns the reinforcement layout number associated with a specified layout
index. The reinforcement layout indices are stored internally and are based on a
contiguous numbering system.

**Syntax**

```c
long St7GetReinforcementLayoutNumByIndex(long uID, long
Index, long* LayoutNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Index` — Reinforcement layout index.

**Output Parameters**

- `LayoutNum` — Reinforcement layout number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_InvalidIndex,
ERR7_NoError
```


---

### `St7NewReinforcementLayout`

Creates a new concrete reinforcement layout.

**Syntax**

```c
long St7NewReinforcementLayout(long uID, long LayoutID,
char* LayoutName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LayoutID` — Layout ID number.
- `LayoutName` — Name of the layout.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLayoutID, ERR7_LayoutIDAlreadyExists,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SetReinforcementName`

Sets the name of the specified concrete reinforcement layout.

**Syntax**

```c
long St7SetReinforcementName(long uID, long LayoutID, char*
LayoutName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LayoutID` — Layout ID number.
- `LayoutName` — Name of the layout.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLayoutID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetReinforcementName`

Returns the names assigned to the specified concrete reinforcement layout.

**Syntax**

```c
long St7GetReinforcementName(long uID, long LayoutID, char*
LayoutName, long MaxStringLen)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LayoutID` — Layout ID number.
- `MaxStringLen` — Maximum number of characters allocated to LayoutName.

**Output Parameters**

- `LayoutName` — Name of the layout.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLayoutID, ERR7_NoError
```


---

### `St7SetReinforcementData`

Sets the concrete reinforcement data for the specified concrete reinforcement
layout.

**Syntax**

```c
long St7SetReinforcementData(long uID, long LayoutID, long*
Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LayoutID` — Layout ID number.
- `Integers[0..7]` — [ipReoLayoutType] - Layup type, either crReoSymmetric or crReoAntiSymmetric. [ipReoColour13] - Layer 13 colour as a 32 bit RGB value. [ipReoColour24] - Layer 24 colour as a 32 bit RGB value. [ipReoCalcMethod] either crReoSimplified or crReoElastoPlasticIter. [ipReoConsiderMembrane] - Consider membrane effects, either btTrue or btFalse. [ipReoAllowCompressionReo] - Allow the steel reinforcement to support compression, either btTrue or btFalse. [ipReoCode] - either 0 for EC2 or 1 for AS 3600. [ipReoLimitConcreteStrain] - Add reinforcement to limit concrete strain, either btTrue or btFalse.
- `Doubles[0..18]` — [ipReoDiam1] - Layer 1 bar diameter. [ipReoDiam2] - Layer 2 bar diameter. [ipReoDiam3] - Layer 3 bar diameter. [ipReoDiam4] - Layer 4 bar diameter. [ipReoCover1] - Cover 1 depth. [ipReoCover2] - Cover 2 depth. [ipReoSpacing1] - Layer 1 bar spacing. [ipReoSpacing2] - Layer 2 bar spacing. [ipReoSpacing3] - Layer 3 bar spacing. [ipReoSpacing4] - Layer 4 bar spacing. [ipReoConcreteModulus] - Concrete modulus. [ipReoConcreteStrain] - Concrete strain limit. [ipReoConcreteStress] - Concrete stress limit. [ipReoConcretePhi] - Concrete phi parameter. [ipReoConcreteGamma] - Concrete gamma parameter. [ipReoSteelModulus] - Steel modulus. [ipReoSteelStress] - Steel stress limit. [ipReoSteelGamma] - Steel gamma parameter. [ipReoSteelMinArea] - Steel minimum area value.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLayoutID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetReinforcementData`

Returns the concrete reinforcement data assigned to the specified concrete
reinforcement layout.

**Syntax**

```c
long St7GetReinforcementData(long uID, long LayoutID, long*
Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LayoutID` — Layout ID number.

**Output Parameters**

- `Integers[0..7]` — [ipReoLayoutType] - Layup type, either crReoSymmetric or crReoAntiSymmetric. [ipReoColour13] - Layer 13 colour as a 32 bit RGB value. [ipReoColour24] - Layer 24 colour as a 32 bit RGB value. [ipReoCalcMethod] either crReoSimplified or crReoElastoPlasticIter. [ipReoConsiderMembrane] - Consider membrane effects, either btTrue or btFalse. [ipReoAllowCompressionReo] - Allow the steel reinforcement to support compression, either btTrue or btFalse. [ipReoCode] - either 0 for EC2 or 1 for AS 3600. [ipReoLimitConcreteStrain] - Add reinforcement to limit concrete strain, either btTrue or btFalse.
- `Doubles[0..18]` — [ipReoDiam1] - Layer 1 bar diameter. [ipReoDiam2] - Layer 2 bar diameter. [ipReoDiam3] - Layer 3 bar diameter. [ipReoDiam4] - Layer 4 bar diameter. [ipReoCover1] - Cover 1 depth. [ipReoCover2] - Cover 2 depth. [ipReoSpacing1] - Layer 1 bar spacing. [ipReoSpacing2] - Layer 2 bar spacing. [ipReoSpacing3] - Layer 3 bar spacing. [ipReoSpacing4] - Layer 4 bar spacing. [ipReoConcreteModulus] - Concrete modulus. [ipReoConcreteStrain] - Concrete strain limit. [ipReoConcreteStress] - Concrete stress limit. [ipReoConcretePhi] - Concrete phi parameter. [ipReoConcreteGamma] - Concrete gamma parameter. [ipReoSteelModulus] - Steel modulus. [ipReoSteelStress] - Steel stress limit. [ipReoSteelGamma] - Steel gamma parameter. [ipReoSteelMinArea] - Steel minimum area value.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLayoutID, ERR7_NoError
```
