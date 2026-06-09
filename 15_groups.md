---
title: "Groups"
source: "Strand7 R246 API Manual"
pages: 143–149
---

# Groups

Coordinate Systems


---

### `St7GetGroupIDName`

Returns the name of a specified group in a Strand7 model.

**Syntax**

```c
long St7GetGroupIDName(long uID, long ID, char* GName, long
MaxStringLen)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `ID` — The ID of the specified group.
- `MaxStringLen` — The maximum number of characters allocated for GName.

**Output Parameters**

- `GName` — String containing the name of the group.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_GroupIdDoesNotExist,
ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7GetNumGroups`

Returns the number of groups in a Strand7 model.

**Syntax**

```c
long St7GetNumGroups(long uID, long* NumGroups)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `NumGroups` — The number of groups in the model.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7GetGroupByIndex`

Returns the group name and ID number corresponding to a specified index.

**Syntax**

```c
long St7GetGroupByIndex(long uID, long Index, char* GName,
long MaxStringLen, long* GroupID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Index` — The index of the specified group. The list of group indices in the model is always contiguous, starting from one.
- `MaxStringLen` — The maximum number of characters allocated for GName.

**Output Parameters**

- `GName` — String containing the name of the specified group.
- `GroupID` — The ID number corresponding to the specified group. Group ID numbers are not required to be contiguous.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_GroupIdDoesNotExist,
ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7NewChildGroup`

Creates a new child group within the specified group parent after its last child.

**Syntax**

```c
long St7NewChildGroup(long uID, long ParentID, char* GName,
long* ChildID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `ParentID` — The ID number for the parent group.
- `GName` — String containing the name of the new group.

**Output Parameters**

- `ChildID` — The ID number for the newly created group.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_GroupIdDoesNotExist,
ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7GetGroupParent`

Returns the parent of a specified group. ParentID is -1 if the specified group is the
root group.

**Syntax**

```c
long St7GetGroupParent(long uID, long GroupID, long*
ParentID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `GroupID` — The ID number of the specified child group.

**Output Parameters**

- `ParentID` — The ID number of the parent group.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_GroupIdDoesNotExist,
ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7GetGroupChild`

Returns the first child of a specified group. ChildID is -1 if the specified group has
no children.

**Syntax**

```c
long St7GetGroupChild(long uID, long GroupID, long*
ChildID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `GroupID` — The ID number of the specified parent group.

**Output Parameters**

- `ChildID` — The ID number of the group child.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_GroupIdDoesNotExist,
ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7GetGroupSibling`

Returns the next sibling of a specified group. SiblingID is -1 if the specified group
has no subsequent siblings.

**Syntax**

```c
long St7GetGroupSibling(long uID, long GroupID, long*
SiblingID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `GroupID` — The ID number of the specified group.

**Output Parameters**

- `SiblingID` — The ID number of the group sibling.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_GroupIdDoesNotExist,
ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7DeleteGroup`

Deletes the specified group. Elements in the group will be reassigned to the
Model group.

**Syntax**

```c
long St7DeleteGroup(long uID, long GroupID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `GroupID` — The ID number of the group to delete.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_GroupIdDoesNotExist,
ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetGroupColour`

Sets the colour of the specified group for entity display purposes.

**Syntax**

```c
long St7SetGroupColour(long uID, long GroupID, long
GroupCol)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `GroupID` — The ID number of the specified group.
- `GroupCol` — Group colour as a 32 bit RGB value.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_GroupIdDoesNotExist,
ERR7_InvalidFileUnit, ERR7_NoError
```
