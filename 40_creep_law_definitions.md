---
title: "Creep Law Definitions"
source: "Strand7 R246 API Manual"
pages: 646–679
---

# Creep Law Definitions

---

### `St7DeleteReinforcementLayout`

Deletes the specified concrete reinforcement layout.

**Syntax**

```c
long St7DeleteReinforcementLayout(long uID, long LayoutID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LayoutID` — Layout ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLayoutID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetTotalCreepDefinitions`

Returns the total number and highest ID number of the creep laws in the
specified model.

**Syntax**

```c
long St7GetTotalCreepDefinitions(long uID, long* NumSets,
long* LastSet)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `NumSets` — The total number of creep laws in the model.
- `LastSet` — The highest creep definition ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7GetCreepDefinitionNumByIndex`

Returns the creep law number associated with a specified creep law index. The
creep law indices are stored internally and are based on a contiguous
numbering system.

**Syntax**

```c
long St7GetCreepDefinitionNumByIndex(long uID, long Index,
long* CreepNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Index` — Creep law index.

**Output Parameters**

- `CreepNum` — Creep law number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_InvalidIndex,
ERR7_NoError
```


---

### `St7NewCreepDefinition`

Creates a new creep law definition.

**Syntax**

```c
long St7NewCreepDefinition(long uID, long CreepID, char*
CreepDefinitionName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CreepID` — Creep definition ID number.
- `CreepDefinitionName` — Name of the creep definition.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CreepIDAlreadyExists, ERR7_FileNotOpen,
ERR7_InvalidCreepID, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetCreepDefinitionName`

Sets the name of the specified creep law definition.

**Syntax**

```c
long St7SetCreepDefinitionName(long uID, long CreepID,
char* CreepDefinitionName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CreepID` — Creep definition ID number.
- `CreepDefinitionName` — Name of the creep definition.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidCreepID,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetCreepDefinitionName`

Returns the name of the specified creep law definition.

**Syntax**

```c
long St7GetCreepDefinitionName(long uID, long CreepID,
char* CreepDefinitionName, long MaxStringLen)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CreepID` — Creep definition ID number.
- `MaxStringLen` — Maximum number of characters allocated for CreepDefinitionName.

**Output Parameters**

- `CreepDefinitionName` — Name of the creep definition.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidCreepID,
ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetCreepLaw`

Sets the type of creep law assigned to the specified creep definition.

**Syntax**

```c
long St7SetCreepLaw(long uID, long CreepID, long CreepLaw)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CreepID` — Creep definition ID number.
- `CreepLaw` — Type of creep law, one of clConcreteHyperbolic, clConcreteViscoChain, clConcreteUserDefined, clPrimaryPower, clSecondaryPower, clPrimarySecondaryPower, clSecondaryHyperbolic, clSecondaryExponential, clThetaProjection, clGenGraham, clGenBlackburn, clUserDefined.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidCreepID,
ERR7_InvalidCreepLaw, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetCreepLaw`

Returns the type of creep law assigned to the specified creep definition.

**Syntax**

```c
long St7GetCreepLaw(long uID, long CreepID, long* CreepLaw)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CreepID` — Creep definition ID number.

**Output Parameters**

- `CreepLaw` — Type of creep law, one of clConcreteHyperbolic, clConcreteViscoChain, clConcreteUserDefined, clPrimaryPower, clSecondaryPower, clPrimarySecondaryPower, clSecondaryHyperbolic, clSecondaryExponential, clThetaProjection, clGenGraham, clGenBlackburn, clUserDefined.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidCreepID,
ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetCreepBasicData`

Sets the basic creep coefficients for the specified creep law definition.

**Syntax**

```c
long St7SetCreepBasicData(long uID, long CreepID, double*
Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CreepID` — Creep definition ID number.
- `Doubles[0..15]` — An array containing the basic creep coefficients. See Creep Definitions for additional information.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidCreepID,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetCreepBasicData`

Returns the basic creep coefficients assigned to the specified creep definition.

**Syntax**

```c
long St7GetCreepBasicData(long uID, long CreepID, double*
Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CreepID` — Creep definition ID number.

**Output Parameters**

- `Doubles[0..15]` — An array containing the basic creep coefficients. See Creep Definitions for additional information.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidCreepID,
ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7EnableCreepUserTable`

Enables a user defined Strain vs Time table for the specified creep law definition.

**Syntax**

```c
long St7EnableCreepUserTable(long uID, long CreepID, long
TableID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CreepID` — Creep definition ID number.
- `TableID` — User defined Strain vs Time table ID.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidCreepID,
ERR7_InvalidFileUnit, ERR7_InvalidTableType, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_TableDoesNotExist
```


---

### `St7DisableCreepUserTable`

Disables a user defined Strain vs Time table for the specified creep law definition.

**Syntax**

```c
long St7DisableCreepUserTable(long uID, long CreepID, long
TableID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CreepID` — Creep definition ID number.
- `TableID` — User defined Strain vs Time table ID.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidCreepID,
ERR7_InvalidFileUnit, ERR7_InvalidTableType, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_TableDoesNotExist
```


---

### `St7GetCreepUserTableState`

Returns the state of a user defined Strain vs Time table for the specified creep law
definition.

**Syntax**

```c
long St7GetCreepUserTableState(long uID, long CreepID, long
TableID, bool* State)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CreepID` — Creep definition ID number.
- `TableID` — User defined Strain vs Time table ID.

**Output Parameters**

- `State` — btTrue if the user defined table is enabled.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidCreepID,
ERR7_InvalidFileUnit, ERR7_InvalidTableType, ERR7_NoError,
ERR7_TableDoesNotExist
```


---

### `St7SetCreepUserTableData`

Sets the data associated with the user defined Strain vs Time data for the
specified creep law definition.

**Syntax**

```c
long St7SetCreepUserTableData(long uID, long CreepID, long
TableID, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CreepID` — Creep definition ID number.
- `TableID` — User defined table ID.
- `Doubles[0..1]` — [0] - Stress level associated with Strain vs Time data. [1] - Temperature associated with Strain vs Time data.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidCreepID,
ERR7_InvalidFileUnit, ERR7_InvalidTableType, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_TableDoesNotExist
```


---

### `St7GetCreepUserTableData`

Returns the data associated with the user defined Strain vs Time table assigned to
the specified creep law definition.

**Syntax**

```c
long St7GetCreepUserTableData(long uID, long CreepID, long
TableID, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CreepID` — Creep definition ID number.
- `TableID` — User defined table ID.

**Output Parameters**

- `Doubles[0..1]` — [0] - Stress level associated with Strain vs Time data. [1] - Temperature associated with Strain vs Time data.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidCreepID,
ERR7_InvalidFileUnit, ERR7_InvalidTableType, ERR7_NoError,
ERR7_TableDoesNotExist
```


---

### `St7SetCreepHardeningType`

Sets the hardening type for the specified creep law definition.

**Syntax**

```c
long St7SetCreepHardeningType(long uID, long CreepID, long*
Integers)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CreepID` — Creep definition ID number.
- `Integers[0..1]` — [ipCreepHardeningType] - Type of creep hardening, either crHardeningTime or crHardeningStrain. [ipCreepHardeningCyclic] - Cyclic hardening option, either btTrue or btFalse.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidCreepHardeningLaw, ERR7_InvalidCreepID,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetCreepHardeningType`

Returns the hardening type assigned to the specified creep law definition.

**Syntax**

```c
long St7GetCreepHardeningType(long uID, long CreepID, long*
Integers)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CreepID` — Creep definition ID number.

**Output Parameters**

- `Integers[0..1]` — [ipCreepHardeningType] - Type of creep hardening, either crHardeningTime or crHardeningStrain. [ipCreepHardeningCyclic] - Cyclic hardening option, either btTrue or btFalse.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidCreepID,
ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetCreepTimeUnit`

Sets the time units for the specified metallic creep law definition.

**Syntax**

```c
long St7SetCreepTimeUnit(long uID, long CreepID, long*
Integers)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CreepID` — Creep definition ID number.
- `Integers[0..0]` — [0] - Time units, one of tuMilliSec, tuSec, tuMin, tuHour or tuDay.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidCreepID,
ERR7_InvalidFileUnit, ERR7_InvalidTimeUnit, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetCreepTimeUnit`

Returns the time units for the specified metallic creep law definition.

**Syntax**

```c
long St7GetCreepTimeUnit(long uID, long CreepID, long*
Integers)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CreepID` — Creep definition ID number.

**Output Parameters**

- `Integers[0..0]` — [0] - Time units, one of tuMilliSec, tuSec, tuMin, tuHour or tuDay.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidCreepID,
ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetCreepTemperatureInclude`

Sets temperature dependency for the specified creep law definition, where
applicable.

**Syntax**

```c
long St7SetCreepTemperatureInclude(long uID, long CreepID,
bool Include)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CreepID` — Creep definition ID number.
- `Include` — btTrue to include temperature dependent terms.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidCreepID,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetCreepTemperatureInclude`

Returns the temperature dependency for the specified creep law definition,
where applicable.

**Syntax**

```c
long St7GetCreepTemperatureInclude(long uID, long CreepID,
bool* Include)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CreepID` — Creep definition ID number.

**Output Parameters**

- `Include` — returns btTrue when temperature dependent terms are included.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidCreepID,
ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetCreepConcreteHyperbolicData`

Sets the hyperbolic data for the specified creep law definition.

**Syntax**

```c
long St7SetCreepConcreteHyperbolicData(long uID, long
CreepID, long* Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CreepID` — Creep definition ID number.
- `Integers[0..1]` — [ipCreepHyperbolicTimeTable] - Factor vs Time table ID, zero for none. [ipCreepHyperbolicConstModulus] - Constant modulus flag, either btTrue or btFalse.
- `Doubles[0..3]` — [ipCreepHyberbolicAlpha] - Hyperbolic law alpha parameter. [ipCreepHyperbolicBeta] - Hyperbolic law beta parameter. [ipCreepHyperbolicDelta] - Hyperbolic law delta parameter. [ipCreepHyperbolicPhi] - Hyperbolic law phi parameter.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidCreepID,
ERR7_InvalidFileUnit, ERR7_InvalidTableType, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_TableDoesNotExist
```


---

### `St7GetCreepConcreteHyperbolicData`

Returns the hyperbolic data assigned to the specified creep law definition.

**Syntax**

```c
long St7GetCreepConcreteHyperbolicData(long uID, long
CreepID, long* Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CreepID` — Creep definition ID number.

**Output Parameters**

- `Integers[0..1]` — [ipCreepHyperbolicTimeTable] - Factor vs Time table ID, zero for none. [ipCreepHyperbolicConstModulus] - Constant modulus flag, either btTrue or btFalse.
- `Doubles[0..3]` — [ipCreepHyberbolicAlpha] - Hyperbolic law alpha parameter. [ipCreepHyperbolicBeta] - Hyperbolic law beta parameter. [ipCreepHyperbolicDelta] - Hyperbolic law delta parameter. [ipCreepHyperbolicPhi] - Hyperbolic law phi parameter.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidCreepID,
ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetCreepConcreteViscoChainData`

Sets the visco-elastic chain data for the specified creep law definition.

**Syntax**

```c
long St7SetCreepConcreteViscoChainData(long uID, long
CreepID, long Pos, long* Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CreepID` — Creep definition ID number.
- `Pos` — Chain number.
- `Integers[0..1]` — [ipCreepViscoTimeTable] - Strain vs Time table ID, zero for none. [ipCreepViscoTempTable] - Factor vs Temperature table ID, zero for none.
- `Doubles[0..1]` — [ipCreepViscoDamper] - Damping value. [ipCreepViscoStiffness] - Stiffness value.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidCreepID,
ERR7_InvalidCreepViscoChainRow, ERR7_InvalidFileUnit,
ERR7_InvalidTableType, ERR7_NoError, ERR7_ResultFileIsOpen,
ERR7_TableDoesNotExist
```


---

### `St7GetCreepConcreteViscoChainData`

Returns the visco-elastic chain data assigned to the specified creep law
definition.

**Syntax**

```c
long St7GetCreepConcreteViscoChainData(long uID, long
CreepID, long Pos, long* Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CreepID` — Creep definition ID number.
- `Pos` — Chain number.

**Output Parameters**

- `Integers[0..1]` — [ipCreepViscoTimeTable] - Strain vs Time table ID, zero for none. [ipCreepViscoTempTable] - Factor vs Temperature table ID, zero for none.
- `Doubles[0..1]` — [ipCreepViscoDamper] - Damping value. [ipCreepViscoStiffness] - Stiffness value.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidCreepID,
ERR7_InvalidCreepViscoChainRow, ERR7_InvalidFileUnit,
ERR7_NoError
```


---

### `St7EnableCreepConcreteUserTable`

Enables the user defined concrete Strain vs Time table for the specified creep law
definition.

**Syntax**

```c
long St7EnableCreepConcreteUserTable(long uID, long CreepID,
long TableID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CreepID` — Creep definition ID number.
- `TableID` — User defined Strain vs Time table ID.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidCreepID,
ERR7_InvalidFileUnit, ERR7_InvalidTableType, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_TableDoesNotExist
```


---

### `St7DisableCreepConcreteUserTable`

Disables the user defined concrete Strain vs Time table for the specified creep
law definition.

**Syntax**

```c
long St7DisableCreepConcreteUserTable(long uID, long
CreepID, long TableID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CreepID` — Creep definition ID number.
- `TableID` — User defined Strain vs Time table ID.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidCreepID,
ERR7_InvalidFileUnit, ERR7_InvalidTableType, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_TableDoesNotExist
```


---

### `St7GetCreepConcreteUserTableState`

Returns the state of the user defined concrete Strain vs Time table for the
specified creep law definition.

**Syntax**

```c
long St7GetCreepConcreteUserTableState(long uID, long
CreepID, long TableID, bool* State)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CreepID` — Creep definition ID number.
- `TableID` — User defined Strain vs Time table ID.

**Output Parameters**

- `State` — btTrue if the user defined concrete table is enabled.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidCreepID,
ERR7_InvalidFileUnit, ERR7_InvalidTableType, ERR7_NoError,
ERR7_TableDoesNotExist
```


---

### `St7SetCreepConcreteUserTableData`

Sets the data for the user defined concrete Strain vs Time table for the specified
creep law definition.

**Syntax**

```c
long St7SetCreepConcreteUserTableData(long uID, long
CreepID, long TableID, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CreepID` — Creep definition ID number.
- `TableID` — User defined Strain vs Time table ID.
- `Doubles[0..1]` — [0] - Age at first loading value. [1] - Stress value associated with Strain vs Time data.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidCreepID,
ERR7_InvalidFileUnit, ERR7_InvalidTableType, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_TableDoesNotExist
```


---

### `St7GetCreepConcreteUserTableData`

Returns the data assigned to the user defined Strain vs Time concrete table for
the specified creep law definition.

**Syntax**

```c
long St7GetCreepConcreteUserTableData(long uID, long
CreepID, long TableID, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CreepID` — Creep definition ID number.
- `TableID` — User defined Strain vs Time table ID.

**Output Parameters**

- `Doubles[0..1]` — [0] - Age at first loading value. [1] - Stress value associated with Strain vs Time data.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidCreepID,
ERR7_InvalidFileUnit, ERR7_InvalidTableType, ERR7_NoError,
ERR7_TableDoesNotExist
```


---

### `St7SetCreepConcreteFunctionType`

Sets the concrete type assigned to the specified creep law definition.

**Syntax**

```c
long St7SetCreepConcreteFunctionType(long uID, long CreepID,
long FunctionType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CreepID` — Creep definition ID number.
- `FunctionType` — Function type, either cfCreepFunction or cfRelaxationFunction.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidCreepFunctionType, ERR7_InvalidCreepID,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetCreepConcreteFunctionType`

Returns the concrete type assigned to the specified creep law definition.

**Syntax**

```c
long St7GetCreepConcreteFunctionType(long uID, long CreepID,
long* FunctionType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CreepID` — Creep definition ID number.

**Output Parameters**

- `FunctionType` — Function type, either cfCreepFunction or cfRelaxationFunction.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidCreepID,
ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetCreepConcreteLoadingAge`

Sets the default loading age for the specified creep law definition.

**Syntax**

```c
long St7SetCreepConcreteLoadingAge(long uID, long CreepID,
double LoadingAge)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CreepID` — Creep definition ID number.
- `LoadingAge` — Default creep loading age.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidCreepID,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetCreepConcreteLoadingAge`

Returns the default loading age assigned to the specified creep law definition.

**Syntax**

```c
long St7GetCreepConcreteLoadingAge(long uID, long CreepID,
double* LoadingAge)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CreepID` — Creep definition ID number.

**Output Parameters**

- `LoadingAge` — Default creep loading age.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidCreepID,
ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetCreepConcreteLoadingTimeUnit`

Sets the time units for the specified concrete creep law definition.

**Syntax**

```c
long St7SetCreepConcreteLoadingTimeUnit(long uID, long
CreepID, long* Integers)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CreepID` — Creep definition ID number.
- `Integers[0..0]` — [0] - Time units, one of tuMilliSec, tuSec, tuMin, tuHour or tuDay.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidCreepID,
ERR7_InvalidFileUnit, ERR7_InvalidTimeUnit, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetCreepConcreteLoadingTimeUnit`

Returns the time units for the specified concrete creep law definition.

**Syntax**

```c
long St7GetCreepConcreteLoadingTimeUnit(long uID, long
CreepID, long* Integers)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CreepID` — Creep definition ID number.

**Output Parameters**

- `Integers[0..0]` — [0] - Time units, one of tuMilliSec, tuSec, tuMin, tuHour or tuDay.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidCreepID,
ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetCreepConcreteShrinkageType`

Sets the shrinkage type assigned to the specified creep law definition.

**Syntax**

```c
long St7SetCreepConcreteShrinkageType(long uID, long
CreepID, long ShrinkageType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CreepID` — Creep definition ID number.
- `ShrinkageType` — Shrinkage type, either crCreepShrinkageTable or crCreepShrinkageFormula.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidCreepID,
ERR7_InvalidCreepShrinkageType, ERR7_InvalidFileUnit,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetCreepConcreteShrinkageType`

Returns the shrinkage type assigned to the specified creep law definition.

**Syntax**

```c
long St7GetCreepConcreteShrinkageType(long uID, long
CreepID, long* ShrinkageType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CreepID` — Creep definition ID number.

**Output Parameters**

- `ShrinkageType` — Shrinkage type, either crCreepShrinkageTable or crCreepShrinkageFormula.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidCreepID,
ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetCreepConcreteShrinkageFormulaData`

Assigns the shrinkage formula data for the specified creep law definition.

**Syntax**

```c
long St7SetCreepConcreteShrinkageFormulaData(long uID, long
CreepID, long* Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CreepID` — Creep definition ID number.
- `Integers[0]` — Currently unused, a dummy integer may be passed.
- `Doubles[0..3]` — [ipCreepShrinkageAlpha] - Concrete shrinkage alpha parameter. [ipCreepShrinkageBeta] - Concrete shrinkage beta parameter. [ipCreepShrinkageDelta] - Concrete shrinkage delta parameter. [ipCreepShrinkageStrain] - Concrete shrinkage initial strain parameter.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidCreepID,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetCreepConcreteShrinkageFormulaData`

Returns the shrinkage formula data assigned to the specified creep law definition.

**Syntax**

```c
long St7GetCreepConcreteShrinkageFormulaData(long uID, long
CreepID, long* Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CreepID` — Creep definition ID number.

**Output Parameters**

- `Integers[0]` — Currently unused, a dummy integer may be passed.
- `Doubles[0..3]` — [ipCreepShrinkageAlpha] - Concrete shrinkage alpha parameter. [ipCreepShrinkageBeta] - Concrete shrinkage beta parameter. [ipCreepShrinkageDelta] - Concrete shrinkage delta parameter. [ipCreepShrinkageStrain] - Concrete shrinkage initial strain parameter.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidCreepID,
ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetCreepConcreteShrinkageTableData`

Associates a table with the concrete shrinkage data for the specified creep law
definition.

**Syntax**

```c
long St7SetCreepConcreteShrinkageTableData(long uID, long
CreepID, long TableID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CreepID` — Creep definition ID number.
- `TableID` — Strain vs Time table ID, zero for none.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidCreepID,


ERR7_InvalidFileUnit, ERR7_InvalidTableType, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_TableDoesNotExist
```


---

### `St7GetCreepConcreteShrinkageTableData`

Returns the table associated with the concrete shrinkage data for the specified
creep law definition.

**Syntax**

```c
long St7GetCreepConcreteShrinkageTableData(long uID, long
CreepID, long* TableID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CreepID` — Creep definition ID number.

**Output Parameters**

- `TableID` — Strain vs Time table ID, zero for none.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidCreepID,
ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetCreepConcreteTemperatureData`

Sets the concrete temperature data for the specified creep law definition.

**Syntax**

```c
long St7SetCreepConcreteTemperatureData(long uID, long
CreepID, long* Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CreepID` — Creep definition ID number.
- `Integers[0..2]` — [ipIncludeCreepTemperature] - Include temperature effects for the creep ageing, either btTrue or btFalse. [ipIncludeRateTemperature] - Include temperature effects for the creep rate, either btTrue or btFalse. [ipIncludeShrinkageTemperature] - Included temperature effects for the shrinkage ageing, either btTrue or btFalse.
- `Doubles[0..5]` — [ipCreepCAAge] - Creep age CA parameter. [ipCreepTRefAge] - Creep age TAREF parameter. [ipCreepCCCreep] - Creep rate CC parameter. [ipCreepTRefCreep] - Creep rate TCREF parameter. [ipCreepCAShrink] - Shrinkage age CA parameter. [ipCreepTRefShrink] - Shrinkage age TAREF parameter.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidCreepID,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetCreepConcreteTemperatureData`

Returns the concrete temperature data associated with the specified creep law
definition.

**Syntax**

```c
long St7GetCreepConcreteTemperatureData(long uID, long
CreepID, long* Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CreepID` — Creep definition ID number.

**Output Parameters**

- `Integers[0..2]` — [ipIncludeCreepTemperature] - Include temperature effects for the creep ageing, either btTrue or btFalse. [ipIncludeRateTemperature] - Include temperature effects for the creep rate, either btTrue or btFalse. [ipIncludeShrinkageTemperature] - Include temperature effects for the shrinkage ageing, either btTrue or btFalse.
- `Doubles[0..5]` — [ipCreepCAAge] - Creep age CA parameter. [ipCreepTRefAge] - Creep age TAREF parameter. [ipCreepCCCreep] - Creep rate CC parameter. [ipCreepTRefCreep] - Creep rate TCREF parameter. [ipCreepCAShrink] - Shrinkage age CA parameter. [ipCreepTRefShrink] - Shrinkage age TAREF parameter.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidCreepID,
ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetCreepConcreteCementCuringData`

Sets the cement curing data for the specified creep law definition.

**Syntax**

```c
long St7SetCreepConcreteCementCuringData(long uID, long
CreepID, long* Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CreepID` — Creep definition ID number.
- `Integers[0..2]` — [ipCreepIncludeCuring] - Include curing effects, either btTrue or btFalse. [ipCreepCuringTimeTable] - Factor vs Time table ID, zero for none. [ipCreepCuringType] - Curing rate, one of ctCuringRapid, ctCuringNormal or ctCuringSlow.
- `Doubles[0..2]` — [ipCreepCuringCT] - Curing CT parameter. [ipCreepCuringTRef] - Curing TREF parameter. [ipCreepCuringT0] - Curing T0 parameter.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidCementHardeningType, ERR7_InvalidCreepID,
ERR7_InvalidFileUnit, ERR7_InvalidTableType, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_TableDoesNotExist
```


---

### `St7GetCreepConcreteCementCuringData`

Returns the cement curing data associated with the specified creep law
definition.

**Syntax**

```c
long St7GetCreepConcreteCementCuringData(long uID, long
CreepID, long* Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CreepID` — Creep definition ID number.

**Output Parameters**

- `Integers[0..2]` — [ipCreepIncludeCuring] - Include curing effects, either btTrue or btFalse. [ipCreepCuringTimeTable] - Factor vs Time table ID, zero for none. [ipCreepCuringType] - Curing rate, one of ctCuringRapid, ctCuringNormal or ctCuringSlow.
- `Doubles[0..2]` — [ipCreepCuringCT] - Curing CT parameter. [ipCreepCuringTRef] - Curing TREF parameter. [ipCreepCuringT0] - Curing T0 parameter.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidCreepID,
ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7DeleteCreepDefinition`

Deletes the specified creep definition.

**Syntax**

```c
long St7DeleteCreepDefinition(long uID, long CreepID)
```
