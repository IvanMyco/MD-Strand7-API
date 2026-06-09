---
title: "Tables"
source: "Strand7 R246 API Manual"
pages: 725–737
---

# Tables

Material Property Libraries
Input Parameters

uID
Strand7 model file ID number.

LayoutID
Concrete reinforcement layout ID number.

LibraryID
Library ID number.

ItemID
Item ID number.
Errors

ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLayoutID, ERR7_InvalidLibraryID,
ERR7_InvalidLibraryItemID, ERR7_NoError,
ERR7_ResultFileIsOpen


---

### `St7GetNumTables`

Returns the number of tables of a specified type in the model.

**Syntax**

```c
long St7GetNumTables(long uID, long TableType, long*
NumTables, long* MaxTableNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `TableType` — Table type, one of ttVsTime, ttVsTemperature, ttVsFrequency, ttStressStrain, ttForceDisplacement, ttMomentCurvature, ttMomentRotation, ttAccVsTime, ttForceVelocity, ttVsPosition or ttStrainTime.

**Output Parameters**

- `NumTables` — Number of tables.
- `MaxTableNum` — Maximum table ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidTableType, ERR7_NoError
```


---

### `St7GetTableInfoByIndex`

Returns the name and ID number of the specified table. The maximum table
index is returned by the St7GetNumTables function.

**Syntax**

```c
long St7GetTableInfoByIndex(long uID, long TableType, long
Index, long* TableID, char* TableName, long
MaxStringLen)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `TableType` — Type of the table, one of ttVsTime, ttVsTemperature, ttVsFrequency, ttStressStrain, ttForceDisplacement, ttMomentCurvature, ttMomentRotation, ttAccVsTime, ttForceVelocity, ttVsPosition or ttStrainTime.
- `Index` — Table index.
- `MaxStringLen` — The maximum number of characters allocated for TableName.

**Output Parameters**

- `TableID` — Table ID number.
- `TableName` — Name of the table.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidTableType, ERR7_NoError, ERR7_TableDoesNotExist
```


---

### `St7NewTableType`

Creates a new table in the specified model.

**Syntax**

```c
long St7NewTableType(long uID, long TableType, long TableID,
long NumEntries, char* TableName, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `TableType` — Type of the table, one of ttVsTime, ttVsTemperature, ttVsFrequency, ttStressStrain, ttForceDisplacement, ttMomentCurvature, ttMomentRotation, ttAccVsTime, ttForceVelocity, ttVsPosition or ttStrainTime.
- `TableID` — Table ID number.
- `NumEntries` — Number of rows (or XY data pairs) in the table.
- `TableName` — Name of the table.
- `Doubles[0..2*NumEntries-1]` — An array containing the XY data for the table. Each XY pair is stored in a block of length 2, with the start of the ith pair at Doubles[(i-1)*2].

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidNumberOfEntries, ERR7_InvalidTableID,
ERR7_InvalidTableName, ERR7_InvalidTableType, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_TableNameAlreadyExists
```


---

### `St7DeleteTableType`

Deletes the specified table.

**Syntax**

```c
long St7DeleteTableType(long uID, long TableType, long
TableID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `TableType` — Type of the table, one of ttVsTime, ttVsTemperature, ttVsFrequency, ttStressStrain, ttForceDisplacement, ttMomentCurvature, ttMomentRotation, ttAccVsTime, ttForceVelocity, ttVsPosition or ttStrainTime.
- `TableID` — Table ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidTableType, ERR7_NoError, ERR7_ResultFileIsOpen,
ERR7_TableDoesNotExist
```


---

### `St7GetTableTypeName`

Returns the name of the specified table.

**Syntax**

```c
long St7GetTableTypeName(long uID, long TableType, long
TableID, char* TableName, long MaxStringLen)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `TableType` — Type of the table, one of ttVsTime, ttVsTemperature, ttVsFrequency, ttStressStrain, ttForceDisplacement, ttMomentCurvature, ttMomentRotation, ttAccVsTime, ttForceVelocity, ttVsPosition or ttStrainTime.
- `TableID` — Table ID number.
- `MaxStringLen` — Maximum number of characters allocated for TableName.

**Output Parameters**

- `TableName` — Name of the table.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidTableType, ERR7_NoError, ERR7_TableDoesNotExist
```


---

### `St7GetTableID`

Returns the ID number for a table specified by name. Where multiple names exist,
the table ID with the lowest table index is returned.

**Syntax**

```c
long St7GetTableID(long uID, char* TableName, long
TableType, long* TableID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `TableName` — Name of the table.
- `TableType` — Type of the table, one of ttVsTime, ttVsTemperature, ttVsFrequency, ttStressStrain, ttForceDisplacement, ttMomentCurvature, ttMomentRotation, ttAccVsTime, ttForceVelocity, ttVsPosition or ttStrainTime.

**Output Parameters**

- `TableID` — Table ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidTableType, ERR7_NoError, ERR7_TableDoesNotExist
```


---

### `St7GetNumTableTypeRows`

Returns the number of rows in the specified table.

**Syntax**

```c
long St7GetNumTableTypeRows(long uID, long TableType, long
TableID, long* NumRows)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `TableType` — Type of the table, one of ttVsTime, ttVsTemperature, ttVsFrequency, ttStressStrain, ttForceDisplacement, ttMomentCurvature, ttMomentRotation, ttAccVsTime, ttForceVelocity, ttVsPosition or ttStrainTime.
- `TableID` — Table ID number.

**Output Parameters**

- `NumRows` — Number of rows.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidTableType, ERR7_NoError, ERR7_TableDoesNotExist
```


---

### `St7SetTableTypeData`

Sets the XY data for the specified table.

**Syntax**

```c
long St7SetTableTypeData(long uID, long TableType, long
TableID, long NumEntries, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `TableType` — Type of the table, one of ttVsTime, ttVsTemperature, ttVsFrequency, ttStressStrain, ttForceDisplacement, ttMomentCurvature, ttMomentRotation, ttAccVsTime, ttForceVelocity, ttVsPosition or ttStrainTime.
- `TableID` — Table ID number.
- `NumEntries` — Number of entries in table.
- `Doubles[0..2*NumEntries-1]` — An array containing the XY data for the table. Each XY pair is stored in a block of length 2, with the start of the ith pair at Doubles[(i-1)*2].

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidNumberOfEntries, ERR7_InvalidTableType,
ERR7_NoError, ERR7_ResultFileIsOpen, ERR7_TableDoesNotExist
```


---

### `St7GetTableTypeData`

Returns the XY data for the specified table.

**Syntax**

```c
long St7GetTableTypeData(long uID, long TableType, long
TableID, long MaxRows, long* NumRows, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `TableType` — Type of the table, one of ttVsTime, ttVsTemperature, ttVsFrequency, ttStressStrain, ttForceDisplacement, ttMomentCurvature, ttMomentRotation, ttAccVsTime, ttForceVelocity, ttVsPosition or ttStrainTime.
- `TableID` — Table ID number.
- `MaxRows` — Maximum number of rows allocated for Doubles.

**Output Parameters**

- `NumRows` — Number of rows used.
- `Doubles[0..2*MaxRows-1]` — An array containing the XY data for the table. Each XY pair is stored in a block of length 2, with the start of the ith pair at Doubles[(i-1)*2].

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidTableType, ERR7_NoError, ERR7_TableDoesNotExist
```


---

### `St7SetFrequencyTable`

Sets the type of the specified Factor vs Frequency table.

**Syntax**

```c
long St7SetFrequencyTable(long uID, long TableID, long
FreqType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `TableID` — Table ID number.
- `FreqType` — Type of frequency table, either tyPeriod or tyFrequency.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidFrequencyType, ERR7_NoError,
ERR7_NotFrequencyTable, ERR7_ResultFileIsOpen,
ERR7_TableDoesNotExist
```


---

### `St7GetFrequencyTable`

Returns the type of the specified Factor vs Frequency table.

**Syntax**

```c
long St7GetFrequencyTable(long uID, long TableID, long*
FreqType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `TableID` — Table ID number.

**Output Parameters**

- `FreqType` — Type of frequency table, either tyPeriod or tyFrequency.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_NotFrequencyTable, ERR7_TableDoesNotExist
```


---

### `St7SetTimeTableUnits`

Sets the time units for the specified time based table.

**Syntax**

```c
long St7SetTimeTableUnits(long uID, long TableType, long
TableID, long UnitType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `TableType` — Type of the table, one of ttVsTime or ttStrainTime.
- `TableID` — Table ID number.
- `UnitType` — Time units, one of tuMilliSec, tuSec, tuMin, tuHour or tuDay.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidTableType, ERR7_InvalidTimeUnit, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_TableDoesNotExist,
ERR7_TableTypeIsNotTimeBased
```


---

### `St7GetTimeTableUnits`

Returns the time units assigned to the specified time based table.

**Syntax**

```c
long St7GetTimeTableUnits(long uID, long TableType, long
TableID, long* UnitType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `TableType` — Type of the table, one of ttVsTime or ttStrainTime.
- `TableID` — Table ID number.

**Output Parameters**

- `UnitType` — Time units, one of tuMilliSec, tuSec, tuMin, tuHour or tuDay.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidTableType, ERR7_NoError, ERR7_TableDoesNotExist,
ERR7_TableTypeIsNotTimeBased
```


---

### `St7ConvertTimeTableUnits`

Converts the time units for the specified time based table.

**Syntax**

```c
long St7ConvertTimeTableUnits(long uID, long TableType,
long TableID, long UnitType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `TableType` — Type of the table, one of ttVsTime, ttVsTemperature, ttVsFrequency, ttStressStrain, ttForceDisplacement, ttMomentCurvature, ttMomentRotation, ttAccVsTime, ttForceVelocity, ttVsPosition or ttStrainTime.
- `TableID` — Table ID number.
- `UnitType` — Time units, one of tuMilliSec, tuSec, tuMin, tuHour or tuDay.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,


ERR7_InvalidTableType, ERR7_InvalidTimeUnit, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_TableDoesNotExist,
ERR7_TableTypeIsNotTimeBased
```


---

### `St7SetFrequencyPeriodTableUnits`

Sets the units assigned to the specified frequency based table.

**Syntax**

```c
long St7SetFrequencyPeriodTableUnits(long uID, long TableID,
long UnitType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `TableID` — Table ID number.
- `UnitType` — Spectrum units type, one of fuNone, fuDispResponse, fuVelResponse, fuAccelResponse, fuDispPSD, fuVelPSD or fuAccelPSD.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_InvalidUnits,
ERR7_InvalidTableType, ERR7_NoError, ERR7_ResultFileIsOpen,
ERR7_TableDoesNotExist
```


---

### `St7GetFrequencyPeriodTableUnits`

Returns the units assigned to the specified frequency based table.

**Syntax**

```c
long St7GetFrequencyPeriodTableUnits(long uID, long TableID,
long* UnitType)
```
