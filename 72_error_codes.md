---
title: "Error Codes"
source: "Strand7 R246 API Manual"
pages: 978–1015
---

# Error Codes

- `kMaxDLPerBeam`







The following lists the error codes that can be returned by function calls to the Strand7
API. The list is broken into two sections: non-solver and solver error codes. The error string
and a description of the errors are included.
Non-Solver Errors


#### `ERR7_InvalidRegionalSettings`
The regional settings, set in the Control Panel/Region and Language are invalid.


#### `ERR7_InvalidDLLsPresent`
SlvPanel.dll and/or St6List.dll are not compatible with St7API.dll.


#### `ERR7_APINotInitialised`
The API is not initialised. St7Init has not been called.


#### `ERR7_InvalidErrorCode`
An invalid error code was requested.


#### `ERR7_APINotLicensed`
The API is not licenced or correctly configured.


#### `ERR7_UnknownError`
An unknown error has occurred.


#### `ERR7_FileAlreadyOpen`
The file is already open.


#### `ERR7_FileNotFound`
File not found.


#### `ERR7_FileNotSt7`
The file is not an St7 file.


#### `ERR7_InvalidFileName`





The file name is not valid.


#### `ERR7_FileIsNewer`
File is newer.


#### `ERR7_CannotReadFile`
Cannot read from file.


#### `ERR7_InvalidScratchPath`
The scratch folder is not valid.


#### `ERR7_FileNotOpen`
The file is not open.


#### `ERR7_ExceededTotal`
The total number of entities was exceeded.


#### `ERR7_DataNotFound`
Data not found.


#### `ERR7_InvalidResultFile`
The file is not a valid St7 result file.


#### `ERR7_ResultFileNotOpen`
The result file is not open.


#### `ERR7_ExceededResultCase`
The total number of result cases was exceeded.


#### `ERR7_UnknownResultType`
The result type is not valid.


#### `ERR7_UnknownResultLocation`
The result location is not valid.


#### `ERR7_UnknownSurfaceLocation`




The surface location is not valid.


#### `ERR7_UnknownProperty`
Unknown property number.


#### `ERR7_InvalidEntity`
Invalid entity.


#### `ERR7_InvalidBeamPosition`
Invalid beam position.


#### `ERR7_InvalidLoadCase`
Invalid load case.


#### `ERR7_InvalidFreedomCase`
Invalid freedom case.


#### `ERR7_UnknownTitle`
Unknown title.


#### `ERR7_UnknownUCS`
Unknown UCS.


#### `ERR7_TooManyBeamStations`
Too many beam stations were specified.


#### `ERR7_UnknownSubType`
Unknown result subtype.


#### `ERR7_GroupIdDoesNotExist`
Group ID does not exist.


#### `ERR7_InvalidFileUnit`
Invalid file unit.


#### `ERR7_CannotSaveFile`




Cannot save file.


#### `ERR7_ResultFileIsOpen`
A result file is open.


#### `ERR7_InvalidUnits`
The unit type specified is invalid.


#### `ERR7_InvalidEntityNodes`
An invalid number of nodes was specified.


#### `ERR7_InvalidUCSType`
The UCS type specified is not valid.


#### `ERR7_InvalidUCSID`
The UCS ID specified is not valid.


#### `ERR7_UCSIDAlreadyExists`
The UCS ID already exists.


#### `ERR7_CaseNameAlreadyExists`
The specified case name already exists.


#### `ERR7_InvalidEntityNumber`
The specified entity number is not valid.


#### `ERR7_InvalidBeamEnd`
The specified beam end is not valid.


#### `ERR7_InvalidBeamDir`
The specified beam direction is not valid.


#### `ERR7_InvalidPlateEdge`
The specified plate edge is not valid.


#### `ERR7_InvalidBrickFace`




The specified brick face is not valid.


#### `ERR7_InvalidBeamType`
The specified beam type is not valid.


#### `ERR7_InvalidPlateType`
The specified plate type is not valid.


#### `ERR7_InvalidMaterialType`
The specified material type is not valid.


#### `ERR7_PropertyAlreadyExists`
The specified property already exists.


#### `ERR7_InvalidBeamSectionType`
The specified beam section type is not valid.


#### `ERR7_PropertyNotSpring`
The specified beam is not a spring.


#### `ERR7_PropertyNotCable`
The specified beam is not a cable.


#### `ERR7_PropertyNotTruss`
The specified beam is not a truss.


#### `ERR7_PropertyNotCutOffBar`
The specified beam is not a cutoff bar.


#### `ERR7_PropertyNotPointContact`
The specified beam is not a point contact.


#### `ERR7_PropertyNotBeam`
The specified beam is not of a beam type.


#### `ERR7_PropertyNotPipe`




The specified beam is not a pipe.


#### `ERR7_PropertyNotConnectionBeam`
The specified beam is not a connection beam.


#### `ERR7_InvalidSectionParameters`
The specified section parameters are not valid.


#### `ERR7_PropertyNotUserDefinedBeam`
The specified beam is not a user defined beam.


#### `ERR7_MaterialIsUserDefined`
The specified property uses a user defined material model.


#### `ERR7_MaterialNotIsotropic`
The specified property does not use an isotropic material model.


#### `ERR7_MaterialNotOrthotropic`
The specified property does not use an orthotropic material model.


#### `ERR7_InvalidRubberModel`
The specified rubber model is not valid.


#### `ERR7_MaterialNotRubber`
The specified property does not use a rubber material model.


#### `ERR7_InvalidSectionProperties`
The specified section properties are not valid.


#### `ERR7_PlateDoesNotHaveThickness`
The specified plate does not have a valid thickness.


#### `ERR7_IncompatibleMaterialCombination`
Incompatible material combination.


#### `ERR7_UnknownSolver`




The specified solver type is not valid.


#### `ERR7_InvalidSolverMode`
The specified solver mode is not valid.


#### `ERR7_InvalidMirrorOption`
The specified mirror option is not valid.


#### `ERR7_SectionCannotBeMirrored`
The section cannot be mirrored.


#### `ERR7_InvalidTableType`
The specified table type is not valid.


#### `ERR7_InvalidTableName`
The specified table name is not valid.


#### `ERR7_TableNameAlreadyExists`
The specified table already exists.


#### `ERR7_InvalidNumberOfEntries`
The specified number of table entries is not valid.


#### `ERR7_InvalidZipType`
The specified zip type is not valid.


#### `ERR7_TableDoesNotExist`
The specified table does not exist.


#### `ERR7_NotFrequencyTable`
The specified table is not a frequency table.


#### `ERR7_InvalidFrequencyType`
The specified frequency type is not valid.


#### `ERR7_InvalidTableSetting`




The specified table setting is not valid.


#### `ERR7_IncompatibleTableType`
The specified table is incompatible with the selected table type.


#### `ERR7_IncompatibleCriterionCombination`
Incompatible yield criterion combination.


#### `ERR7_InvalidModalFile`
The specified modal results file is not valid.


#### `ERR7_InvalidCombinationCaseNumber`
The specified load case combination number is not valid.


#### `ERR7_InvalidInitialCaseNumber`
The specified initial case number is not valid.


#### `ERR7_InvalidInitialFile`
The specified initial file is not valid.


#### `ERR7_InvalidModeNumber`
The specified mode number is not valid.


#### `ERR7_BeamIsNotBXS`
The specified beam property is not a BXS beam.


#### `ERR7_InvalidDampingType`
The specified damping type is not valid.


#### `ERR7_InvalidRayleighMode`
The specified Rayleigh mode is not valid.


#### `ERR7_CannotReadBXS`
The BXS data cannot be read.


#### `ERR7_InvalidResultType`




The specified result type is not valid.


#### `ERR7_InvalidSolverParameter`
The specified solver parameter is not valid.


#### `ERR7_InvalidModalLoadType`
The specified modal load type is not valid.


#### `ERR7_InvalidTimeRow`
The specified time step row is not valid.


#### `ERR7_SparseSolverNotLicenced`
The sparse solver is not licenced.


#### `ERR7_InvalidSolverScheme`
The specified solver storage scheme is not valid.


#### `ERR7_InvalidSortOption`
The specified sort option is not valid.


#### `ERR7_IncompatibleResultFile`
The current result file is incompatible with the requested result.


#### `ERR7_InvalidLinkType`
The specified link type is not valid.


#### `ERR7_InvalidLinkData`
The specified link data is not valid.


#### `ERR7_OnlyOneLoadCase`
The model contains only one load case, which cannot be deleted.


#### `ERR7_OnlyOneFreedomCase`
The model contains only one freedom case, which cannot be deleted.


#### `ERR7_InvalidLoadID`




The specified load ID is not valid.


#### `ERR7_InvalidBeamLoadType`
The specified load type is not valid.


#### `ERR7_InvalidStringID`
The specified string ID is not valid.


#### `ERR7_InvalidPatchType`
The specified patch type is not valid.


#### `ERR7_IncrementDoesNotExist`
The specified increment does not exist.


#### `ERR7_InvalidLoadCaseType`
The specified load case type is not valid.


#### `ERR7_InvalidFreedomCaseType`
The specified freedom case type is not valid.


#### `ERR7_InvalidHarmonicLoadType`
The specified harmonic load type is not valid.


#### `ERR7_InvalidTemperatureType`
The specified temperature type is not valid.


#### `ERR7_InvalidPatchTypeForPlate`
The specified patch type is not valid for the selected element.


#### `ERR7_InvalidAttributeType`
The specified attribute type is not valid.


#### `ERR7_MaterialNotAnisotropic`
The specified property does not use an anisotropic material model.


#### `ERR7_InvalidMatrixType`




The specified matrix type is not valid.


#### `ERR7_MaterialNotUserDefined`
The specified property does not use a user defined material model.


#### `ERR7_InvalidIndex`
The requested index is outside the allowable range.


#### `ERR7_InvalidContactType`
The specified contact type is not valid.


#### `ERR7_InvalidContactSubType`
The specified contact subtype is not valid.


#### `ERR7_InvalidCutoffType`
The specified cutoff type is not valid.


#### `ERR7_ResultQuantityNotAvailable`
The result quantity requested is not available.


#### `ERR7_YieldNotMCDP`
The yield criterion for the specified property is not Mohr Coulomb or Drucker Prager.


#### `ERR7_CombinationDoesNotExist`
The specified combination does not exist.


#### `ERR7_InvalidSeismicCase`
The specified seismic case is not valid.


#### `ERR7_InvalidImportExportMode`
The specified export mode is not valid.


#### `ERR7_CannotReadImportFile`
The import file cannot be read.


#### `ERR7_InvalidAnsysImportFormat`




The specified ANSYS import format is not valid.


#### `ERR7_InvalidAnsysArrayStatus`
The specified ANSYS array status is not valid.


#### `ERR7_CannotWriteExportFile`
The export file cannot be written.


#### `ERR7_InvalidAnsysExportFormat`
The specified ANSYS export format is not valid.


#### `ERR7_InvalidAnsysEndReleaseOption`
The specified ANSYS End Release option is not valid.


#### `ERR7_InvalidAnsysExportUnits`
The specified ANSYS export units is not valid.


#### `ERR7_InvalidSt7ExportFormat`
The specified ST7 export format is not valid.


#### `ERR7_InvalidUVPos`
The u-v position specified is not valid.


#### `ERR7_InvalidResponseType`
The response type specified is not valid.


#### `ERR7_InvalidLayoutID`
The specified concrete layout ID is not valid.


#### `ERR7_InvalidPlateSurface`
The specified plate surface is not valid.


#### `ERR7_MeshingErrors`
Surface meshing has generated an error.


#### `ERR7_InvalidZipTolerance`




The specified zip tolerance is not valid.


#### `ERR7_InvalidTaperAxis`
The specified taper axis is not valid.


#### `ERR7_InvalidTaperType`
The specified taper type is not valid.


#### `ERR7_InvalidTaperRatio`
The specified taper ratios are not valid.


#### `ERR7_InvalidPositionType`
The specified position type is not valid.


#### `ERR7_InvalidPreLoadType`
The specified pre-load type is not valid.


#### `ERR7_InvalidVertexType`
The specified vertex type is not valid.


#### `ERR7_InvalidVertexMeshSize`
The specified vertex mesh size is not valid.


#### `ERR7_InvalidGeometryEdgeType`
The specified geometry edge type is not valid.


#### `ERR7_InvalidPropertyNumber`
The specified property number is not valid.


#### `ERR7_InvalidFaceSurface`
The specified geometry face surface is not valid.


#### `ERR7_InvalidModType`
The specified time dependent modulus type is not valid.


#### `ERR7_MaterialNotSoil`




The specified property does not use a soil material model.


#### `ERR7_MaterialNotFluid`
The specified property does not use a fluid material model.


#### `ERR7_SoilTypeNotDC`
The specified property does not use a Duncan-Chang soil material model.


#### `ERR7_SoilTypeNotCC`
The specified property does not use a Cam-Clay soil material model.


#### `ERR7_MaterialNotLaminate`
The specified property does not use a laminate material model.


#### `ERR7_InvalidLaminateID`
The specified laminate ID is not valid.


#### `ERR7_LaminateNameAlreadyExists`
The specified laminate name already exists.


#### `ERR7_LaminateIDAlreadyExists`
The specified laminate ID already exists.


#### `ERR7_PlyDoesNotExist`
The specified ply does not exist.


#### `ERR7_ExceededMaxNumPlies`
The maximum number of plies was exceeded.


#### `ERR7_LayoutIDAlreadyExists`
The specified concrete layout ID already exists.


#### `ERR7_InvalidNumModes`
The requested number of modes is not valid.


#### `ERR7_InvalidLTAMethod`




The specified linear transient solver method is not valid.


#### `ERR7_InvalidLTASolutionType`
The specified linear transient solver solution type is not valid.


#### `ERR7_ExceededMaxNumStages`
The maximum number of stages was exceeded.


#### `ERR7_StageDoesNotExist`
The specified stage does not exist.


#### `ERR7_ExceededMaxNumSpectralCases`
The maximum number of spectral cases was exceeded.


#### `ERR7_InvalidSpectralCase`
The specified spectral case is not valid.


#### `ERR7_InvalidSpectrumType`
The specified spectrum type is not valid.


#### `ERR7_InvalidResultsSign`
The specified results sign is not valid.


#### `ERR7_InvalidPositionTableAxis`
The specified position table axis is not valid.


#### `ERR7_InvalidInitialConditionsType`
The specified initial conditions type is not valid.


#### `ERR7_ExceededMaxNumNodeHistory`
The maximum number of node history definitions was exceeded.


#### `ERR7_NodeHistoryDoesNotExist`
The specified node history does not exist.


#### `ERR7_InvalidTransientTempType`




The specified transient temperature input type is not valid.


#### `ERR7_InvalidTimeUnit`
The time unit type specified is not valid.


#### `ERR7_InvalidLoadPath`
The specified load path is not valid.


#### `ERR7_InvalidTempDependenceType`
The specified temperature dependence type is not valid.


#### `ERR7_InvalidTrigType`
The specified trigonometric type is not valid.


#### `ERR7_InvalidUserEquation`
The specified user equation is not valid.


#### `ERR7_InvalidCreepID`
The specified creep definition ID is not valid.


#### `ERR7_CreepIDAlreadyExists`
The specified creep definition ID already exists.


#### `ERR7_InvalidCreepLaw`
The specified creep law is not valid.


#### `ERR7_InvalidCreepHardeningLaw`
The specified creep hardening law is not valid.


#### `ERR7_InvalidCreepViscoChainRow`
The specified creep visco-elastic data row is not valid.


#### `ERR7_InvalidCreepFunctionType`
The specified creep function/chain type is not valid.


#### `ERR7_InvalidCreepShrinkageType`




The specified creep shrinkage type is not valid.


#### `ERR7_InvalidTableRow`
The specified table row is not valid.


#### `ERR7_ExceededMaxNumRows`
The maximum number of rows was exceeded.


#### `ERR7_InvalidLoadPathTemplateID`
The specified load path template ID is not valid.


#### `ERR7_LoadPathTemplateIDAlreadyExists`
The specified load path template ID already exists.


#### `ERR7_InvalidLoadPathLane`
The specified load path template lane is not valid.


#### `ERR7_ExceededMaxNumLoadPathTemplates`
The maximum number of load path templates was exceeded.


#### `ERR7_ExceededMaxNumLoadPathVehicles`
The maximum number of vehicles was exceeded.


#### `ERR7_InvalidLoadPathVehicle`
The specified load path template vehicle is not valid.


#### `ERR7_InvalidMobilityType`
The specified mobility type is not valid.


#### `ERR7_InvalidAxisSystem`
The specified axis system is not valid.


#### `ERR7_InvalidLoadPathID`
The specified load path ID is not valid.


#### `ERR7_LoadPathIDAlreadyExists`




The specified load path ID already exists.


#### `ERR7_InvalidPathDefinition`
The path definition is not valid.


#### `ERR7_InvalidLoadPathShape`
The specified load path shape is not valid.


#### `ERR7_InvalidLoadPathSurface`
The specified load path surface is not valid.


#### `ERR7_InvalidNumPathDivs`
The specified number of path divisions is not valid.


#### `ERR7_InvalidGeometryCavityLoop`
The specified geometry face cavity loop is not valid.


#### `ERR7_InvalidLimitEnvelope`
The specified limit envelope is not valid.


#### `ERR7_ExceededMaxNumLimitEnvelopes`
The maximum number of limit envelopes was exceeded.


#### `ERR7_InvalidCombEnvelope`
The specified combination envelope is not valid.


#### `ERR7_ExceededMaxNumCombEnvelopes`
The maximum number of combination envelopes was exceeded.


#### `ERR7_InvalidFactorsEnvelope`
The specified factors envelope is not valid.


#### `ERR7_ExceededMaxNumFactorsEnvelopes`
The maximum number of factors envelopes was exceeded.


#### `ERR7_InvalidLimitEnvelopeType`




The specified limit envelope type is not valid.


#### `ERR7_InvalidCombEnvelopeType`
The specified combination envelope type is not valid.


#### `ERR7_InvalidFactorsEnvelopeType`
The specified factors envelope type is not valid.


#### `ERR7_InvalidCombEnvelopeAccType`
The specified combination envelope accumulation type is not valid.


#### `ERR7_InvalidEnvelopeSet`
The specified envelope set is not valid.


#### `ERR7_ExceededMaxNumEnvelopeSets`
The maximum number of envelope sets was exceeded.


#### `ERR7_InvalidEnvelopeSetType`
The specified envelope set type is not valid.


#### `ERR7_InvalidCombResFile`
The specified combination result file is not valid.


#### `ERR7_ExceededMaxNumCombResFiles`
The maximum number of combination result files was exceeded.


#### `ERR7_CannotCombResFiles`
The result files cannot be combined.


#### `ERR7_InvalidStartEndTimes`
The specified start and end times are not valid.


#### `ERR7_InvalidNumSteps`
The specified number of steps is not valid.


#### `ERR7_InvalidLibraryPath`




The library folder is not valid.


#### `ERR7_InvalidLibraryType`
The specified library type is not valid.


#### `ERR7_InvalidLibraryID`
The specified library ID is not valid.


#### `ERR7_InvalidLibraryName`
The specified library name is not valid.


#### `ERR7_InvalidLibraryItemID`
The specified library item ID is not valid.


#### `ERR7_InvalidLibraryItemName`
The specified library item name is not valid.


#### `ERR7_InvalidDisplayOptionsPath`
The configuration file folder is not valid.


#### `ERR7_InvalidSolverPath`
The solver folder is not valid.


#### `ERR7_InvalidCementHardeningType`
The specified cement hardening type is not valid.


#### `ERR7_ZeroPlateElements`
The model contains zero plate elements.


#### `ERR7_CannotMakeBXS`
The beam section cannot be generated.


#### `ERR7_CannotCalculateBXSData`
The beam section data cannot be calculated.


#### `ERR7_InvalidSurfaceMeshTargetType`




The specified plate element target is not valid.


#### `ERR7_InvalidModalNodeReactType`
The specified node reaction type is not valid.


#### `ERR7_InvalidAxis`
The specified axis is not valid.


#### `ERR7_InvalidBeamAxisType`
The specified beam axis type is not valid.


#### `ERR7_InvalidStaadCountryCodeOption`
The specified STAAD country code option is not valid.


#### `ERR7_InvalidGeometryFormatProtocol`
The specified geometry format/protocol is not valid.


#### `ERR7_InvalidDXFBeamOption`
The specified DXF beam option is not valid.


#### `ERR7_InvalidDXFPlateOption`
The specified DXF plate option is not valid.


#### `ERR7_InvalidLoadPathLaneFactorType`
The specified load path template multi-lane factor type is not valid.


#### `ERR7_InvalidLoadPathVehicleInstance`
The specified load path template vehicle instance type is not valid.


#### `ERR7_InvalidNumBeamStations`
The specified number of beam stations is not valid.


#### `ERR7_ResFileUnsupportedType`
The specified solution type is not supported.


#### `ERR7_ResFileAlreadyOpen`




The result file is already open.


#### `ERR7_ResFileInvalidNumCases`
The specified number of result cases is not valid.


#### `ERR7_ResFileNotOpen`
The result file is not open.


#### `ERR7_ResFileInvalidCase`
The specified result case is not valid.


#### `ERR7_ResFileDoesNotHaveEntity`
The model does not contain this entity.


#### `ERR7_ResFileInvalidQuantity`
The specified result quantity is not valid.


#### `ERR7_ResFileQuantityNotExist`
The result file does not contain the specified result quantity.


#### `ERR7_ResFileCantSave`
The result file cannot be saved.


#### `ERR7_ResFileCantClearQuantity`
The specified quantity must always exist in a result file.


#### `ERR7_ResFileContainsNoElements`
The model does not contain any elements.


#### `ERR7_ResFileContainsNoNodes`
The model does not contain any nodes.


#### `ERR7_ResFileInvalidName`
The specified result file name is not valid.


#### `ERR7_ResFileAssociationNotAllowed`




Load and freedom case association is not supported by this result file type.


#### `ERR7_ResFileIncompatibleQuantity`
The specified quantity is not compatible with the result file type.


#### `ERR7_CannotEditSolverFiles`
Result files generated directly by the solver cannot be edited.


#### `ERR7_CannotOpenResultFile`
The result file cannot be opened.


#### `ERR7_CouldNotShowModelWindow`
The model window could not be displayed.


#### `ERR7_ModelWindowWasNotShowing`
The model window was not showing.


#### `ERR7_CantDoWithModalWindows`
Operation cannot be performed when modal dialogs are open.


#### `ERR7_InvalidSelectionEndEdgeFace`
The specified end, edge or face is not valid.


#### `ERR7_CouldNotCreateModelWindow`
The model window could not be created.


#### `ERR7_ModelWindowWasNotCreated`
The model window has not been created.


#### `ERR7_InvalidImageType`
The specified image type is not valid.


#### `ERR7_InvalidImageDimensions`
The specified image dimensions are not valid.


#### `ERR7_InsufficientRamToCreateImage`




Insufficient RAM to create image.


#### `ERR7_CannotSaveImageFile`
Cannot save image file.


#### `ERR7_InvalidWindowDimensions`
The specified window dimensions are not valid.


#### `ERR7_InvalidResultQuantity`
The specified quantity is not valid.


#### `ERR7_InvalidResultSubQuantity`
The specified sub-quantity is not valid.


#### `ERR7_InvalidComponent`
The specified component is not valid.


#### `ERR7_ResultIsNotAvailable`
The result is not available.


#### `ERR7_InvalidUCSIndex`
The specified UCS index is not valid.


#### `ERR7_InvalidDiagramAxis`
The specified diagram axis is not valid.


#### `ERR7_InvalidVectorComponents`
The specified vector component is not valid.


#### `ERR7_TableTypeIsNotTimeBased`
The specified table is not time based.


#### `ERR7_InvalidTableID`
The specified table ID is not valid.


#### `ERR7_LinkNotMasterSlave`




The specified link is not a master-slave link.


#### `ERR7_LinkNotSectorSymmetry`
The specified link is not a sector symmetry link.


#### `ERR7_LinkNotCoupling`
The specified link is not a coupling link.


#### `ERR7_LinkNotPinned`
The specified link is not a pinned link.


#### `ERR7_LinkNotRigid`
The specified link is not a rigid link.


#### `ERR7_LinkNotShrink`
The specified link is not a shrink link.


#### `ERR7_LinkNotTwoPoint`
The specified link is not a 2-point link.


#### `ERR7_LinkNotAttachment`
The specified link is not an attachment link.


#### `ERR7_LinkNotMultiPoint`
The specified link is not a multi-point link.


#### `ERR7_InvalidCoupleType`
The specified couple type is not valid.


#### `ERR7_InvalidRigidPlane`
The specified rigid plane is not valid.


#### `ERR7_InvalidMultiPointFactorsType`
The specified multi-point link factors type is not valid.


#### `ERR7_InvalidMultiPointLink`




The specified multi-point link is not valid.


#### `ERR7_InvalidAttachmentType`
The specified attachment type is not valid.


#### `ERR7_ExceededMaxNumColumns`
The maximum number of columns was exceeded.


#### `ERR7_CouldNotDestroyModelWindow`
The model window could not be destroyed.


#### `ERR7_CannotSetWindowParent`
Cannot set the specified model window parent.


#### `ERR7_InvalidLoadCaseFilePath`
The ANSYS load case file folder is not valid.


#### `ERR7_InvalidStaadLengthUnit`
The specified STAAD length unit is not valid.


#### `ERR7_InvalidStaadForceUnit`
The specified STAAD force unit is not valid.


#### `ERR7_InvalidDuplicateFaceType`
The specified duplicate face type is not valid.


#### `ERR7_InvalidNodeCoordinateKeepType`
The specified node coordinate keep type is not valid.


#### `ERR7_CommentDoesNotExist`
The specified comment does not exist.


#### `ERR7_InvalidFilePath`
The file path is not valid.


#### `ERR7_InvalidContactYieldType`




The specified contact yield type is not valid.


#### `ERR7_InvalidNumMeshingLoops`
The specified number of loops is not valid.


#### `ERR7_InvalidMeshPositionOnUCS`
The specified UCS position is not valid.


#### `ERR7_InvalidK0Expression`
Invalid K0 expression.


#### `ERR7_InvalidK1Expression`
Invalid K1 expression.


#### `ERR7_NoPatchLoadsCreated`
No patch loads were generated.


#### `ERR7_InvalidResOptsBeamEnvelope`
The specified beam envelope setting is invalid.


#### `ERR7_InvalidResOptsRotationUnit`
The specified rotation unit is invalid.


#### `ERR7_InvalidResOptsHRASetting`
The specified Harmonic Response Analysis result settings are invalid.


#### `ERR7_InvalidResOptsStageDisplacement`
The specified Staged Analysis displacement result setting is invalid.


#### `ERR7_InvalidToolOptsZipOptions`
The specified zip settings are invalid.


#### `ERR7_InvalidToolOptsSubdivideOptions`
The specified subdivide settings are invalid.


#### `ERR7_InvalidToolOptsCopyOptions`




The specified copy settings are invalid.


#### `ERR7_InvalidToleranceType`
The specified tolerance type is invalid.


#### `ERR7_InvalidAttachPartsParams`
Invalid attach parts parameters.


#### `ERR7_InvalidDrawParameters`
Invalid entity display parameters.


#### `ERR7_FilesStillOpen`
There are files still open.


#### `ERR7_SolverStillRunning`
There are solvers still running.


#### `ERR7_InvalidPolygonToFaceParameters`
Invalid polygon to face parameters.


#### `ERR7_InvalidResOptsStrainUnit`
Invalid strain unit.


#### `ERR7_FunctionNotSupported`
Function no longer supported.


#### `ERR7_SoilTypeNotMC`
The specified property does not use a Mohr-Coulomb soil material model.


#### `ERR7_SoilTypeNotDP`
The specified property type does not use a Drucker-Prager soil material model.


#### `ERR7_TooManyAnimations`
Maximum number of animations are already running.


#### `ERR7_InvalidAnimationFile`




The file is not a valid animation file.


#### `ERR7_InvalidAnimationMode`
The specified animation mode is not valid.


#### `ERR7_InsufficientFrames`
The specified number of frames is not sufficient to generate an animation.


#### `ERR7_AnimationDimensionsTooSmall`
Animation dimension is too small.


#### `ERR7_AnimationDimensionsTooLarge`
Animation dimension is too large.


#### `ERR7_ReducedAnimation`
Insufficient memory for complete animation.


#### `ERR7_InvalidAnimationType`
The specified animation file type is not valid.


#### `ERR7_CannotFindStubFile`
The stub file, "animator.stb", required for creating self-running animations, cannot be
found.


#### `ERR7_CouldNotSaveAnimationFile`
An error occurred while saving the animation file.


#### `ERR7_AnimationHandleOutOfRange`
The specified animation handle is outside the valid range.


#### `ERR7_AnimationNotRunning`
The requested animation is not running.


#### `ERR7_SoilTypeNotLS`
The specified property does not use a Linear Elastic soil material model.






#### `ERR7_NoPolygonWasConverted`
No polygon was converted.


#### `ERR7_InvalidAlphaTempType`
The specified alpha vs temperature type is not valid


#### `ERR7_InvalidGravityDirection`
Invalid gravity direction.


#### `ERR7_InvalidAttachmentDirection`
The specified attachment direction is not valid.


#### `ERR7_InvalidHardeningType`
The specified hardening type is not valid.


#### `ERR7_ResultCaseNotInertiaRelief`
The result case is not restrained by inertial relief.


#### `ERR7_InvalidNumLayers`
The number of plate integration layers is invalid (less than 1 or greater than 100).


#### `ERR7_PlateDoesNotHaveLayers`
The plate property does not require integration layers.


#### `ERR7_ToolOperationFailed`
The Strand7 tool operation failed.





Solver Errors

SE_NoLoadCaseSelected
No load case selected.

SE_IncompatibleRestartFile
Incompatible restart file.

SE_ElementUsesInvalidProperty
An element uses an invalid property.

SE_InvalidElement
Model contains an invalid element.

SE_NeedNonlinearHeatSolver
Model requires the nonlinear heat solver.

SE_TableNotFound
A table specified in the model was not found.

SE_InvalidRestartFile
Invalid restart file.

SE_InvalidInitialFile
Invalid initial file.

SE_InvalidSolverResultFile
Invalid solver result file.

SE_InvalidLink
Model contains an invalid link.

SE_InvalidPlateCohesionValue
Invalid plate cohesion value.

SE_InvalidBrickCohesionValue




Invalid brick cohesion value.

SE_NonlinearSolverRequired
Model requires the nonlinear solver.

SE_NoLoadTablesDefined
No load tables defined.

SE_NoVelocityDataInInitialFile
No velocity data in initial file.

SE_NoModesIncluded
No modes included for modal superposition method.

SE_InvalidTimeStep
Invalid time steps used in model.

SE_LoadIncrementsNotDefined
Load increments not defined.

SE_NoFreedomCaseInIncrements
No freedom case in increments.

SE_InvalidInitialTemperatureFile
Invalid initial temperature file.

SE_InvalidFrequencyRange
Invalid frequency range.

SE_ModelMixesAxiNonAxi
Model mixes axisymmetric elements with non-axisymmetric elements.

SE_CompositeModuleNotAvailable
Composite module not available.

SE_CannotFindSolver




Cannot find solver.

SE_UnknownException
Unknown error.

SE_DuplicateLinks
Duplicate links in model.

SE_CannotAppendToFile
Cannot append to file.

SE_CannotOverwriteFile
Cannot overwrite file.

SE_CannotWriteToResultFile
Cannot write to result file.

SE_CannotWriteToLogFile
Cannot write to log file.

SE_CannotReadRestartFile
Cannot read restart file.

SE_InitialConditionsNotValid
Initial conditions are not valid.

SE_InvalidRayleighFactors
Invalid Rayleigh factors.

SE_ShearPanelMustBeQuad4
Shear panel must be Quad4.

SE_SingularPlateMatrix
Singular plate matrix.

SE_SingularBrickMatrix




Singular brick matrix.

SE_NoBeamProperties
No beam properties defined.

SE_NoPlateProperties
No plate properties defined.

SE_NoBrickProperties
No brick properties defined.

SE_MoreLoadIncrementsNeeded
More load increments are required.

SE_RubberRequiresGNL
Rubber material in model requires the geometry nonlinear option.

SE_NoFreedomCaseSelected
No freedom case selected.

SE_InvalidSpectralVectors
Invalid spectral vectors.

SE_NoSpectralResultsSelected
No spectral results selected.

SE_SpectralFactorsNotDefined
Spectral factors are not defined.

SE_SpectralFactorsAllZero
Spectral factors are all zero.

SE_NoTimeStepsSaved
No time steps are saved.

SE_InvalidDirectionVector




Invalid direction vector.

SE_HarmonicFactorsAllZero
Harmonic factors are all zero.

SE_TemperatureDependenceCaseNotSet
Temperature dependence case is not set.

SE_ZeroLengthRigidLinkGenerated
A link of zero length was generated.

SE_InvalidStringGroupDefinition
An invalid string group was found.

SE_InvalidPreTensionOnString
A string group with variable pre-tension was found.

SE_StringOrderHasChanged
The string elements defined in the model are not compatible with those in the restart file.

SE_BadTaperData
Beam element has invalid taper attributes.

SE_TaperedPlasticBeams
Tapered beams do not support material nonlinearity.

SE_NoMovingLoadPathsInCases
No load paths were found in the selected load cases.

SE_NoResponseVariablesDefined
No response variables (entity attributes) have been defined.

SE_InvalidPlateVariableRequested
Plate{s} have one or more invalid response variables assigned.

SE_InvalidGravityCase




The load case selected as the soil/fluid gravity case is not valid.

SE_InvalidUserPlateCreepDefinition
The user defined creep table required by a plate property is not valid.

SE_InvalidUserBrickCreepDefinition
The user defined creep table required by a brick property is not valid.

SE_InvalidPlateShrinkageDefinition
The creep/shrinkage definition required by a plate property is not valid.

SE_InvalidBrickShrinkageDefinition
The creep/shrinkage definition required by a brick property is not valid.

SE_InvalidLaminateID
A plate property references an invalid laminate definition.

SE_CannotReadWriteScratchPath
The scratch path does not have sufficient read/write access to allow the solver to run.

SE_CannotConvertAttachmentLink
Attachment link is not valid as it generates a singular matrix.

SE_SoilRequiresMNL
Soil material in model requires the material nonlinear option.

SE_ActiveStageHasNoIncrements
Load increments are not defined for an active stage.

SE_ConcreteCreepMNL
Concrete creep and material stress-strain tables cannot be considered together.

SE_CannotConvertInterpMultiPoint
Mutlipoint link generated a singular matrix.

SE_MissingInsituStress




Some soil elements do not have in-situ stress attributes – an estimate based on element
depth will be used.

SE_InvalidMaterialNonlinearString
For material nonlinearity, all elements in a string group must use the same property set.

SE_TensileInsituPlateStress
Some soil elements (plates) have tensile (positive) in-situ stress attributes.

SE_TensileInsituBrickStress
Some soil elements (bricks) have tensile (positive) in-situ stress attributes.

SE_IncompatibleRestartUnits
The units in the result file selected for appending are different to the units in the model.

SE_CreepTimeTooShort
Creep curve fit time is too short.

SE_InvalidElements
Elements with invalid connections were found.

SE_InsufficientRestartFileSteps
The restart file contains fewer result cases than the requested restart case.

SE_NeedNodeTempNTASolver
Table Type nodal temperatures are not supported by the linear transient dynamic solver.

SE_SingleShotRestartFile
The restart file contains only the last saved result case.

SE_SkylineUsesBadSort
The Skyline scheme usually works best with the Tree and Geometry node orderings.

SE_StagedSolutionFileNotFound
The file used in the initial staged analysis cannot be found or is invalid.





