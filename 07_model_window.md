---
title: "Model Window"
source: "Strand7 R246 API Manual"
pages: 49–75
---

# Model Window

Entity Selection


---

### `St7GetEntitySelectState`

Returns the select state of a specified entity.

**Syntax**

```c
long St7GetEntitySelectState(long uID, long Entity, long
EntityNum, long EndEdgeFace, bool* Selected)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Entity` — Entity type, one of tyNODE, tyBEAM, tyPLATE, tyBRICK, tyLINK, tyVERTEX, tyGEOMETRYEDGE, tyGEOMETRYFACE or tyLOADPATH.
- `EntityNum` — Entity number.
- `EndEdgeFace` — Local entity number, either 1 or 2 for tyBEAM, one of 1,2,3 or 4 for tyPLATE or 1,2,3,4,5 or 6 for tyBRICK. Use zero to check state of tyNODE and for entire tyBEAM, tyPLATE and tyBRICK.

**Output Parameters**

- `Selected` — Selected state, either btTrue or btFalse.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidSelectionEndEdgeFace, ERR7_NoError
```


---

### `St7CreateModelWindow`

Creates a Strand7 graphical window for a Strand7 model.

**Syntax**

```c
long St7CreateModelWindow(long uID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CouldNotCreateModelWindow, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7DestroyModelWindow`

Destroys the graphical model window for a Strand7 model.

**Syntax**

```c
long St7DestroyModelWindow(long uID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CouldNotDestroyModelWindow, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_ModelWindowWasNotCreated,
ERR7_NoError
```


---

### `St7GetModelWindowState`

Returns the state of the graphical model window for a Strand7 model.

**Syntax**

```c
long St7GetModelWindowState(long uID, long* State)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `State` — Model window state, one of wsModelWindowNotCreated, wsModelWindowVisible, wsModelWindowMaximised, wsModelWindowMinimised or wsModelWindowHidden.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7GetModelWindowHandle`

Returns the handle to the graphical model window.

**Syntax**

```c
long St7GetModelWindowHandle(long uID, long* Handle)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `Handle` — Handle to the graphics window.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_ModelWindowWasNotCreated, ERR7_NoError
```


---

### `St7SetModelWindowParent`

Sets the parent control for the graphical model window. This function can be
used to dock the model window inside another graphical control.

**Syntax**

```c
long St7SetModelWindowParent(long uID, long Handle)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Handle` — Handle to the parent control for the graphics window.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CannotSetWindowParent, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_ModelWindowWasNotCreated,
ERR7_NoError
```


---

### `St7ShowModelWindow`

Shows the graphical model window.

**Syntax**

```c
long St7ShowModelWindow(long uID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CantDoWithModalWindows, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_ModelWindowWasNotCreated,
ERR7_ModelWindowWasNotShowing, ERR7_NoError
```


---

### `St7HideModelWindow`

Hides the graphical model window.

**Syntax**

```c
long St7HideModelWindow(long uID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CantDoWithModalWindows, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_ModelWindowWasNotCreated,
ERR7_ModelWindowWasNotShowing, ERR7_NoError
```


---

### `St7RedrawModel`

Redraws the graphics within the graphical model window.

**Syntax**

```c
long St7RedrawModel(long uID, bool Rescale)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Rescale` — Rescale the view limits when the graphics are redrawn, either btTrue or btFalse.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CantDoWithModalWindows, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_ModelWindowWasNotCreated,
ERR7_ModelWindowWasNotShowing, ERR7_NoError
```


---

### `St7UpdateElementPropertyData`

Updates the display database used by the graphical model window so that a
redraw shows modifications made to entities when St7RedrawModel is used, e.g.
changes to property colours, beam section dimensions, plate thickness, etc.

**Syntax**

```c
long St7UpdateElementPropertyData(long uID, long Entity,
long PropNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Entity` — The property type, either ptBEAMPROP or ptPLATEPROP.
- `PropNum` — The updated property number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntity, ERR7_InvalidFileUnit,
ERR7_NoError, ERR7_ResultFileIsOpen, ERR7_UnknownProperty
```


---

### `St7ClearModelWindow`

Clears the graphics within the graphical model window.

**Syntax**

```c
long St7ClearModelWindow(long uID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CantDoWithModalWindows, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_ModelWindowWasNotCreated,
ERR7_ModelWindowWasNotShowing, ERR7_NoError
```


---

### `St7ShowWindowPopUp`

Enables a menu group in the right-click popup menu available in the model
window.

**Syntax**

```c
long St7ShowWindowPopUp(long uID, long MenuGroup)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `MenuGroup` — Popup menu group ID, one of imView, imDisplay, imShow, imSelect or imResults.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CantDoWithModalWindows, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_ModelWindowWasNotCreated,
ERR7_ModelWindowWasNotShowing, ERR7_NoError
```


---

### `St7HideWindowPopUp`

Disables a menu group in the right-click popup menu available in the model
window.

**Syntax**

```c
long St7HideWindowPopUp(long uID, long MenuGroup)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `MenuGroup` — Popup menu group ID, one of imView, imDisplay, imShow, imSelect or imResults.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CantDoWithModalWindows, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_ModelWindowWasNotCreated,
ERR7_ModelWindowWasNotShowing, ERR7_NoError
```


---

### `St7ShowWindowTopPanel`

Shows the top menu panel within the graphical model window.

**Syntax**

```c
long St7ShowWindowTopPanel(long uID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CantDoWithModalWindows, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_ModelWindowWasNotCreated,
ERR7_ModelWindowWasNotShowing, ERR7_NoError
```


---

### `St7HideWindowTopPanel`

Hides the top menu panel within the graphical model window.

**Syntax**

```c
long St7HideWindowTopPanel(long uID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CantDoWithModalWindows, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_ModelWindowWasNotCreated,
ERR7_ModelWindowWasNotShowing, ERR7_NoError
```


---

### `St7ShowWindowToolbar`

Shows the toolbar within the graphical model window.

**Syntax**

```c
long St7ShowWindowToolbar(long uID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CantDoWithModalWindows, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_ModelWindowWasNotCreated,
ERR7_ModelWindowWasNotShowing, ERR7_NoError
```


---

### `St7HideWindowToolbar`

Hides the toolbar within the graphical model window.

**Syntax**

```c
long St7HideWindowToolbar(long uID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CantDoWithModalWindows, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_ModelWindowWasNotCreated,
ERR7_ModelWindowWasNotShowing, ERR7_NoError
```


---

### `St7ShowWindowStatusBar`

Shows the status bar within the graphical model window.

**Syntax**

```c
long St7ShowWindowStatusBar(long uID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CantDoWithModalWindows, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_ModelWindowWasNotCreated,
ERR7_ModelWindowWasNotShowing, ERR7_NoError
```


---

### `St7HideWindowStatusBar`

Hides the status bar within the graphical model window.

**Syntax**

```c
long St7HideWindowStatusBar(long uID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CantDoWithModalWindows, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_ModelWindowWasNotCreated,
ERR7_ModelWindowWasNotShowing, ERR7_NoError
```


---

### `St7ShowSelectionToolBar`

Shows the selection toolbar when using the graphical model window.

**Syntax**

```c
long St7ShowSelectionToolBar(long uID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CantDoWithModalWindows, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_ModelWindowWasNotCreated,
ERR7_ModelWindowWasNotShowing, ERR7_NoError
```


---

### `St7HideSelectionToolBar`

Hides the selection toolbar when using the graphical model window.

**Syntax**

```c
long St7HideSelectionToolBar(long uID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CantDoWithModalWindows, ERR7_FileNotOpen,


ERR7_InvalidFileUnit, ERR7_ModelWindowWasNotCreated,
ERR7_ModelWindowWasNotShowing, ERR7_NoError
```


---

### `St7SetSelectionToolBarPosition`

Sets the screen position of the selection toolbar.

**Syntax**

```c
long St7SetSelectionToolBarPosition(long uID, long Left,
long Top)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Left` — Pixel position of the left edge of the selection toolbar.
- `Top` — Pixel position of the top edge of the selection toolbar.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CantDoWithModalWindows, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_ModelWindowWasNotCreated,
ERR7_ModelWindowWasNotShowing, ERR7_InvalidWindowDimensions,
ERR7_NoError
```


---

### `St7GetSelectionToolBarPosition`

Returns the screen position of the selection toolbar.

**Syntax**

```c
long St7GetSelectionToolBarPosition(long uID, long* Left,
long* Top)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `Left` — Pixel position of the left edge of the selection toolbar.
- `Top` — Pixel position of the top edge of the selection toolbar.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CantDoWithModalWindows, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_ModelWindowWasNotCreated,
ERR7_ModelWindowWasNotShowing, ERR7_NoError
```


---

### `St7RotateModel`

Sets the view angle for the model within the graphical display window.

**Syntax**

```c
long St7RotateModel(long uID, double RX, double RY, double
RZ)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `RX` — Rotation about the Global X axis in degrees.
- `RY` — Rotation about the Global Y axis in degrees.
- `RZ` — Rotation about the Global Z axis in degrees.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7ShowEntity`

Shows all entities of a specified type within the graphical model window.

**Syntax**

```c
long St7ShowEntity(long uID, long Entity)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Entity` — Strand7 entity type, one of tyNODE, tyBEAM, tyPLATE, tyBRICK, tyLINK, tyVERTEX, tyGEOMETRYEDGE, tyGEOMETRYFACE or tyLOADPATH.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntity, ERR7_InvalidFileUnit,
ERR7_NoError
```


---

### `St7HideEntity`

Hides all entities of a specified type within the graphical model window.

**Syntax**

```c
long St7HideEntity(long uID, long Entity)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Entity` — Strand7 entity type, one of tyNODE, tyBEAM, tyPLATE, tyBRICK, tyLINK, tyVERTEX, tyGEOMETRYEDGE, tyGEOMETRYFACE or tyLOADPATH.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntity, ERR7_InvalidFileUnit,
ERR7_NoError
```


---

### `St7SetEntityDisplay`

Sets the display settings for the specified model entity.

**Syntax**

```c
long St7SetEntityDisplay(long uID, long Entity, long*
Integers)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Entity` — Strand7 entity type, one of tyNODE, tyBEAM, tyPLATE, tyBRICK, tyLINK, tyVERTEX, tyGEOMETRYEDGE, tyGEOMETRYFACE or tyLOADPATH.
- `Integers[0..20]` — See Entity Display Settings for additional information.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CantDoWithModalWindows, ERR7_FileNotOpen,
ERR7_InvalidDrawParameters, ERR7_InvalidEntity,
ERR7_InvalidFileUnit, ERR7_ModelWindowWasNotCreated,
ERR7_ModelWindowWasNotShowing, ERR7_NoError
```


---

### `St7GetEntityDisplay`

Returns the display settings assigned for the specified model entity.

**Syntax**

```c
long St7GetEntityDisplay(long uID, long Entity, long*
Integers)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Entity` — Strand7 entity type, one of tyNODE, tyBEAM, tyPLATE, tyBRICK, tyLINK, tyVERTEX, tyGEOMETRYEDGE, tyGEOMETRYFACE or tyLOADPATH.

**Output Parameters**

- `Integers[0..20]` — See Entity Display Settings for additional information.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CantDoWithModalWindows, ERR7_FileNotOpen,
ERR7_InvalidEntity, ERR7_InvalidFileUnit,
ERR7_ModelWindowWasNotCreated,
ERR7_ModelWindowWasNotShowing, ERR7_NoError
```


---

### `St7ShowPointAttributes`

Shows the node and vertex attributes within the graphical model window.

**Syntax**

```c
long St7ShowPointAttributes(long uID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7HidePointAttributes`

Hides the node and vertex attributes within the graphical model window.

**Syntax**

```c
long St7HidePointAttributes(long uID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7ShowEntityAttributes`

Shows the element attributes within the graphical model window.

**Syntax**

```c
long St7ShowEntityAttributes(long uID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7HideEntityAttributes`

Hides the element attributes within the graphical model window.

**Syntax**

```c
long St7HideEntityAttributes(long uID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7PositionModelWindow`

Sets the screen position of the graphical model window.

**Syntax**

```c
long St7PositionModelWindow(long uID, long Left, long Top,
long Width, long Height)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Left` — Pixel position of the left edge of the model window.
- `Top` — Pixel position of the top edge of the model window.
- `Width` — Pixel width of the model window.
- `Height` — Pixel height of the model window.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidWindowDimensions, ERR7_NoError
```


---

### `St7GetModelWindowPosition`

Returns the screen position of the graphical model window.

**Syntax**

```c
long St7GetModelWindowPosition(long uID, long* Left, long*
Top, long* Width, long* Height)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `Left` — Pixel position of the left edge of the model window.
- `Top` — Pixel position of the top edge of the model window.
- `Width` — Pixel width of the model window.
- `Height` — Pixel height of the model window.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CantDoWithModalWindows, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_ModelWindowWasNotCreated,
ERR7_ModelWindowWasNotShowing, ERR7_NoError
```


---

### `St7GetDrawAreaSize`

Returns the screen area available for drawing the model graphics within the
graphical model window.

**Syntax**

```c
long St7GetDrawAreaSize(long uID, long* Width, long*
Height)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `Width` — Pixel width of the drawing area.
- `Height` — Pixel height of the drawing area.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CantDoWithModalWindows, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_ModelWindowWasNotCreated,
ERR7_ModelWindowWasNotShowing, ERR7_NoError
```


---

### `St7ShowProperty`

Shows all of the entities of a specified property within the graphical model
window.

**Syntax**

```c
long St7ShowProperty(long uID, long Entity, long PropNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Entity` — Strand7 entity type, one of tyNODE, tyBEAM, tyPLATE, tyBRICK, tyLINK, tyVERTEX, tyGEOMETRYEDGE, tyGEOMETRYFACE or tyLOADPATH.
- `PropNum` — The ID number of the property to show.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntity, ERR7_InvalidFileUnit,
ERR7_NoError, ERR7_UnknownProperty
```


---

### `St7HideProperty`

Hides all of the entities of a specified property number within the graphical model
window.

**Syntax**

```c
long St7HideProperty(long uID, long Entity, long PropNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Entity` — Strand7 entity type, one of tyNODE, tyBEAM, tyPLATE, tyBRICK, tyLINK, tyVERTEX, tyGEOMETRYEDGE, tyGEOMETRYFACE or tyLOADPATH.
- `PropNum` — The ID number of the property to hide.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntity, ERR7_InvalidFileUnit,
ERR7_NoError, ERR7_UnknownProperty
```


---

### `St7ShowGroup`

Shows all entities in a specified group within the graphical model window.

**Syntax**

```c
long St7ShowGroup(long uID, long GroupID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `GroupID` — The ID number of the group to show.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_GroupIdDoesNotExist,
ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7HideGroup`

Hides all of the entities in a specified group within the graphical model window.

**Syntax**

```c
long St7HideGroup(long uID, long GroupID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `GroupID` — The ID number of the group to hide.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_GroupIdDoesNotExist,
ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetBeamResultDisplay`

Sets the display options for the beam results within the graphical model window.

**Syntax**

```c
long St7SetBeamResultDisplay(long uID, long* Integers)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Integers[0..12]` — [ipResultType] - Beam result type, one of rtAsNone, rtAsContour, rtAsDiagram or rtAsVector. [ipResultQuantity] - See Result Display Options. [ipResultAxis] - See Result Display Options. [ipResultComponent] - See Result Display Options. [ipVectorStyle] - Vector display style, one of vtVectorComponent, vtVectorTranslationMag, vtVectorRotationMag.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidAxisSystem, ERR7_InvalidAxis,
ERR7_InvalidComponent, ERR7_InvalidDiagramAxis,
ERR7_InvalidFileUnit, ERR7_InvalidResultSubQuantity,
ERR7_InvalidResultType, ERR7_InvalidUCSID,
ERR7_InvalidVectorComponents, ERR7_NoError,
ERR7_ResultFileNotOpen, ERR7_ResultIsNotAvailable
```


---

### `St7SetPlateResultDisplay`

Sets the display options for the plate results within the graphical model window.

**Syntax**

```c
long St7SetPlateResultDisplay(long uID, long* Integers)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Integers[0..12]` — [ipResultType] - Plate result type, one of rtAsNone, rtAsContour, rtAsDiagram or rtAsVector. [ipResultQuantity] - See Result Display Options. [ipResultAxis] - See Result Display Options. [ipResultComponent] - See Result Display Options. [ipResultSurface] - Plate surface display, one of psPlateMidPlane, psPlateZMinus or psPlateZPlus. [ipVectorStyle] - Vector display style, one of vtVectorComponent, vtVectorTranslationMag, vtVectorRotationMag.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidAxisSystem, ERR7_InvalidAxis,
ERR7_InvalidComponent, ERR7_InvalidFileUnit,
ERR7_InvalidPlateSurface, ERR7_InvalidResultSubQuantity,
ERR7_InvalidResultType, ERR7_InvalidUCSID,
ERR7_InvalidVectorComponents, ERR7_NoError,
ERR7_ResultFileNotOpen, ERR7_ResultIsNotAvailable,
ERR7_UnknownSubType
```


---

### `St7SetBrickResultDisplay`

Sets the display options for the brick results within the graphical model window.

**Syntax**

```c
long St7SetBrickResultDisplay(long uID, long* Integers)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Integers[0..12]` — [ipResultType] - Brick result type, one of rtAsNone, rtAsContour, rtAsDiagram or rtAsVector. [ipResultQuantity] - See Result Display Options. [ipResultAxis] - See Result Display Options. [ipResultComponent] - See Result Display Options. [ipVectorStyle] - Vector display style, one of vtVectorComponent, vtVectorTranslationMag, vtVectorRotationMag.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidAxisSystem, ERR7_InvalidAxis,
ERR7_InvalidComponent, ERR7_InvalidFileUnit,
ERR7_InvalidResultSubQuantity, ERR7_InvalidResultType,
ERR7_InvalidUCSID, ERR7_InvalidVectorComponents,
ERR7_NoError, ERR7_ResultFileNotOpen,
ERR7_ResultIsNotAvailable, ERR7_UnknownSubType
```


---

### `St7SetWindowResultCase`

Sets the result case to be displayed within the graphical model window.

**Syntax**

```c
long St7SetWindowResultCase(long uID, long CaseNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — The result case ID number to be displayed.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CantDoWithModalWindows, ERR7_ExceededResultCase,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_ModelWindowWasNotCreated,
ERR7_ModelWindowWasNotShowing, ERR7_NoError,
ERR7_ResultFileNotOpen
```


---

### `St7SetWindowLoadCase`

Sets the load case to be displayed within the graphical model window.

**Syntax**

```c
long St7SetWindowLoadCase(long uID, long CaseNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — The load case ID number to be displayed.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CantDoWithModalWindows, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_InvalidLoadCase,
ERR7_ModelWindowWasNotCreated,
ERR7_ModelWindowWasNotShowing, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetWindowFreedomCase`

Sets the freedom case to be displayed within the graphical model window.

**Syntax**

```c
long St7SetWindowFreedomCase(long uID, long CaseNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — The freedom case ID number to be displayed.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CantDoWithModalWindows, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_ModelWindowWasNotCreated,
ERR7_ModelWindowWasNotShowing, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetWindowUCSCase`

Sets the UCS case to be displayed within the graphical model window.

**Syntax**

```c
long St7SetWindowUCSCase(long uID, long CaseNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — The UCS ID number to be displayed.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CantDoWithModalWindows, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_InvalidUCSIndex,
ERR7_ModelWindowWasNotCreated,
ERR7_ModelWindowWasNotShowing, ERR7_NoError
```


---

### `St7SetEntityContourFile`

Sets a user defined contour file for beam, plate or brick elements.

**Syntax**

```c
long St7SetEntityContourFile(long uID, long Entity, long
FileType, char* FileName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Entity` — Strand7 entity type to contour, one of tyBEAM, tyPLATE or tyBRICK.
- `FileType` — Basis for the contour values, either ucNode or ucElement.
