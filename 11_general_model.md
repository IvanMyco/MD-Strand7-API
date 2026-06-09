---
title: "General Model"
source: "Strand7 R246 API Manual"
pages: 102–110
---

# General Model

---

### `St7GetAnimationCase`

Returns the state assigned to the specified result case for multi-case animations.

**Syntax**

```c
long St7GetAnimationCase(long uID, long CaseNum, bool*
Active)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — Result case number.

**Output Parameters**

- `Active` — btTrue if the case is included in the animation.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_ExceededResultCase, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileNotOpen
```


---

### `St7GetTotal`

Returns the total number of entities of a specified entity type in a Strand7 model.

**Syntax**

```c
long St7GetTotal(long uID, long Entity, long* Total)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Entity` — Strand7 entity type, one of tyNODE, tyBEAM, tyPLATE, tyBRICK, tyLINK, tyVERTEX, tyGEOMETRYEDGE, tyGEOMETRYFACE or tyLOADPATH.

**Output Parameters**

- `Total` — Total number of entities in the model.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntity, ERR7_InvalidFileUnit,
ERR7_NoError
```


---

### `St7SetTitle`

Sets the title for a Strand7 model.

**Syntax**

```c
long St7SetTitle(long uID, long TitleType, char*
TitleString)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `TitleType` — Title type, one of TITLEModel, TITLEProject, TITLEReference or TITLEAuthor. See Title Types for details.
- `TitleString` — String containing the Strand7 model title.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_UnknownTitle
```


---

### `St7GetTitle`

Returns the title of a Strand7 model.

**Syntax**

```c
long St7GetTitle(long uID, long TitleType, char*
TitleString, long MaxStringLen)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `TitleType` — Title type, one of TITLEModel, TITLEProject, TITLEReference, TITLEAuthor, TITLECreated or TITLEModified. See Title Types for details.
- `MaxStringLen` — Maximum number of characters allocated for TitleString.

**Output Parameters**

- `TitleString` — String containing the Strand7 model title.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_UnknownTitle
```


---

### `St7AddComment`

Appends a comment to the Strand7 model’s comments. Comments are stored
contiguously and are identified by their index, from one up to the total number of
comments.

**Syntax**

```c
long St7AddComment(long uID, char* CommentString)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CommentString` — String containing the comment to be added. Each string is presented as a line in the Strand7 comments dialogue.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7GetNumComments`

Returns the number of comments in a Strand7 model.

**Syntax**

```c
long St7GetNumComments(long uID, long* NumComments)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `NumComments` — Number of comments in the model.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetComment`

Replaces the text in a specified comment of a Strand7 model.

**Syntax**

```c
long St7SetComment(long uID, long Comment, char*
CommentString)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Comment` — Index number of the comment to be replaced.
- `CommentString` — String containing the new comment. Each string is presented as a line in the Strand7 comments dialogue.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_CommentDoesNotExist
```


---

### `St7GetComment`

Returns the specified comment in a Strand7 model.

**Syntax**

```c
long St7GetComment(long uID, long Comment, char*
CommentString, long MaxStringLen)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Comment` — Index number for the comment to be returned.
- `MaxStringLen` — Maximum number of characters allocated for CommentString.

**Output Parameters**

- `CommentString` — String containing the returned comment.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_CommentDoesNotExist
```


---

### `St7DeleteComment`

Deletes the specified comment in a Strand7 model.

**Syntax**

```c
long St7DeleteComment(long uID, long Comment)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Comment` — Index number of the comment to be deleted.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CommentDoesNotExist, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7GetBeamAxisSystem`

Returns the beam axis system for a specified beam element in a Strand7 model.
See Beam Local Coordinates for further information.

**Syntax**

```c
long St7GetBeamAxisSystem(long uID, long EltNum, bool
Initial, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `EltNum` — Beam number
- `Initial` — Use btTrue to return the initial axis system, btFalse will return the updated system due to any geometric nonlinearity in the analysis.

**Output Parameters**

- `Doubles[0..8]` — [0..2] - A unit vector in the 1-direction of the beam, expressed in the global coordinate system. [3..5] - A unit vector in the 2-direction of the beam. [6..8] - A unit vector in the 3-direction of the beam.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_ExceededTotal, ERR7_FileNotOpen,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_NoError
```


---

### `St7GetPlateAxisSystem`

Returns the plate axis system for a specified plate element in a Strand7 model.
See Plate Local Coordinates for further information.

**Syntax**

```c
long St7GetPlateAxisSystem(long uID, long EltNum, bool
Initial, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `EltNum` — Plate number.
- `Initial` — btTrue to return the initial axis system.

**Output Parameters**

- `Doubles[0..8]` — [0..2] - A unit vector in the local x-direction of the plate, expressed in the global coordinate system. [3..5] - A unit vector in the local y-direction of the plate. [6..8] - A unit vector in the local z-direction of the plate.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_ExceededTotal, ERR7_FileNotOpen,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_NoError
```


---

### `St7GetBrickFaceAxisSystem`

Returns the brick face axis system for a specified brick face in a Strand7 model.
See Brick Local Coordinates for further information.

**Syntax**

```c
long St7GetBrickFaceAxisSystem(long uID, long EltNum, long
FaceNum, bool Initial, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `EltNum` — Brick number.
- `FaceNum` — Local face number. See Brick Local Coordinates for further information.
- `Initial` — btTrue to return the initial axis system.

**Output Parameters**

- `Doubles[0..8]` — [0..2] - A unit vector in the local x-direction of the face, expressed in the global coordinate system. [3..5] - A unit vector in the local y-direction of the face. [6..8] - A unit vector in the local z-direction of the face, note this is directed out of the median plane of the face.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_ExceededTotal, ERR7_FileNotOpen, ERR7_InvalidBrickFace,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_NoError
```


---

### `St7GetPlateNumPlies`

Returns the number of plies in a specified plate element in a Strand7 model.
