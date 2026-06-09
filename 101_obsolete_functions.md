---
title: "Obsolete Functions"
source: "Strand7 R246 API Manual"
pages: 1119–1141
---

# Obsolete Functions

Custom Results

ipBrickResFileGXX - Brick temperature gradient in the local x axis direction.
ipBrickResFileGYY - Brick temperature gradient in the local y axis direction.
ipBrickResFileGZZ - Brick temperature gradient in the local z axis direction.
The above constants index contiguous blocks of results for each brick Gauss point, where
each block is kBrickResFileFluxSize long.


There are a number of functions that have become obsolete due to continued
development. For backwards compatibility, these functions will continue to be available
in the Strand7 API, although they will not be fully documented and their continued use is
not recommended. Typically an alternative function will be available, that supports
enhanced functionality.
In rare situations functions may no longer be supported in the Strand7 API. In these cases
the functions will still be available, but will always return the ERR7_FunctionNotSupported
error code. A function will only be discontinued in this way if its behaviour is no longer
valid, otherwise the function will simply become undocumented as described above.
The following list outlines obsolete functions and the recommended alternatives:
St7ZipMesh
Status
Undocumented.
Alternatives
St7CleanMesh, St7SetCleanMeshData, St7GetCleanMeshData.
St7SetBeamSectionProperties
Status
Undocumented.
Alternatives
St7SetBeamSectionPropertyData.
St7CalcBeamSectionProperties
Status
Undocumented.
Alternatives
St7CalculateBeamSectionProperties.
St7AddNonlinearIncrement
Status


Undocumented.
Alternatives
St7AddNLAIncrement.
St7InsertNonlinearIncrement
Status
Undocumented.
Alternatives
St7InsertNLAIncrement.
St7DeleteNonlinearIncrement
Status
Undocumented.
Alternatives
St7DeleteNLAIncrement.
St7SetNonlinearLoadIncrementFactor
Status
Undocumented.
Alternatives
St7SetNLALoadIncrementFactor.
St7SetNonlinearFreedomIncrementFactor
Status
Undocumented.
Alternatives
St7SetNLAFreedomIncrementFactor.
St7GetNonlinearLoadIncrementFactor
Status
Undocumented.


Alternatives
St7GetNLALoadIncrementFactor.
St7GetNonlinearFreedomIncrementFactor
Status
Undocumented.
Alternatives
St7GetNLAFreedomIncrementFactor.
St7AddLoadCaseCombination
Status
Undocumented.
Alternatives
St7AddLSACombination.
St7InsertLoadCaseCombination
Status
Undocumented.
Alternatives
St7InsertLSACombination.
St7DeleteLoadCaseCombination
Status
Undocumented.
Alternatives
St7DeleteLSACombination.
St7SetLoadCaseCombinationFactor
Status
Undocumented.
Alternatives


St7SetLSACombinationFactor.
St7GetLoadCaseCombinationFactor
Status
Undocumented.
Alternatives
St7GetLSACombinationFactor.
St7EnableNonlinearLoadCase
Status
Undocumented.
Alternatives
St7EnableNLALoadCase.
St7DisableNonlinearLoadCase
Status
Undocumented.
Alternatives
St7DisableNLALoadCase.
St7EnableNonlinearFreedomCase
Status
Undocumented.
Alternatives
St7GetNLALoadCaseState, St7EnableNLAFreedomCase.
St7DisableNonlinearFreedomCase
Status
Undocumented.
Alternatives
St7DisableNLAFreedomCase.


St7GetNonlinearLoadCaseState
Status
Undocumented.
Alternatives
St7GetNLALoadCaseState.
St7GetNonlinearFreedomCaseState
Status
Undocumented.
Alternatives
St7GetNLAFreedomCaseState.
St7EnableFrequencyNSMassCase
Status
Undocumented.
Alternatives
St7EnableNFANonStructuralMassCase.
St7DisableFrequencyNSMassCase
Status
Undocumented.
Alternatives
St7DisableNFANonStructuralMassCase.
St7GetFrequencyNSMassCaseState
Status
Undocumented.
Alternatives
St7GetNFANonStructuralMassCaseState.


St7GetBeamResult
Status
Undocumented.
Alternatives
St7GetBeamResultArray, St7GetBeamResultArrayPos,
St7GetBeamResultEndPos, St7GetBeamResultSinglePos.
St7GetBeamForceResultPos
Status
Undocumented.
Alternatives
St7GetBeamResultArray, St7GetBeamResultArrayPos,
St7GetBeamResultEndPos, St7GetBeamResultSinglePos.
St7GetBeamResultPos
Status
Undocumented.
Alternatives
St7GetBeamResultArray, St7GetBeamResultArrayPos,
St7GetBeamResultEndPos, St7GetBeamResultSinglePos.
St7GetBeamDispResultPos
Status
Undocumented.
Alternatives
St7GetBeamResultArray, St7GetBeamResultArrayPos,
St7GetBeamResultEndPos, St7GetBeamResultSinglePos.
St7GetPlateResult
Status
Undocumented.
Alternatives


St7GetPlateResultArray.
St7GetPlateResultUCS
Status
Undocumented.
Alternatives
St7GetPlateResultArray.
St7GetBrickResult
Status
Undocumented.
Alternatives
St7GetBrickResultArray.
St7GetBrickResultUCS
Status
Undocumented.
Alternatives
St7GetBrickResultArray.
St7GetUserSpectralName
Status
Undocumented.
Alternatives
St7GetLSACombinationSpectralName.
St7SetNodeKTranslation3
Status
Undocumented.
Alternatives
St7SetNodeKTranslation3F.


St7SetNodeKRotation3
Status
Undocumented.
Alternatives
St7SetNodeKRotation3F.
St7SetNodeKDamping3
Status
Undocumented.
Alternatives
St7SetNodeKDamping3F.
St7SetNodeNSMass2
Status
Undocumented.
Alternatives
St7SetNodeNSMass5.
St7GetBeamProperty
Status
Undocumented.
Alternatives
St7GetBeamPropertyData.
St7GetPlateProperty
Status
Undocumented.
Alternatives
St7GetPlatePropertyData.


St7GetBrickProperty
Status
Undocumented.
Alternatives
St7GetBrickPropertyData.
St7SetBeamSupport2
Status
Undocumented.
Alternatives
St7SetBeamSupport2F.
St7SetBeamDLL4
Status
Undocumented.
Alternatives
St7SetBeamDLL6ID.
St7SetBeamDML4
Status
Undocumented.
Alternatives
St7SetBeamDML6ID.
St7SetBeamDLG4
Status
Undocumented.
Alternatives
St7SetBeamDLG6ID.


St7SetBeamCFL4
Status
Undocumented.
Alternatives
St7SetBeamCFL4ID.
St7SetBeamCFG4
Status
Undocumented.
Alternatives
St7SetBeamCFG4ID.
St7SetBeamCML4
Status
Undocumented.
Alternatives
St7SetBeamCML4ID.
St7SetBeamCMG4
Status
Undocumented.
Alternatives
St7SetBeamCMG4ID.
St7SetBeamNSMass7ID
Status
Undocumented.
Alternatives
St7SetBeamNSMass10ID.


St7SetPipePressure2
Status
Undocumented.
Alternatives
St7SetPipePressure2AF.
St7SetPipeTemperature2
Status
Undocumented.
Alternatives
St7SetPipeTemperature2OT.
St7SetBeamPreTension1
Status
Undocumented.
Alternatives
St7SetBeamPreLoad1.
St7SetPlatePreStress3
Status
Undocumented.
Alternatives
St7SetPlatePreLoad3.
St7SetPlateFaceSupport1
Status
Undocumented.
Alternatives
St7SetPlateSupport1F.


St7SetPlateEdgeSupport1
Status
Undocumented.
Alternatives
St7SetPlateEdgeSupport1F.
St7SetPlateNSMass2
Status
Undocumented.
Alternatives
St7SetPlateNSMass5.
St7SetPlateConvection2
Status
Undocumented.
Alternatives
St7SetPlateEdgeConvection2.
St7SetPlateRadiation2
Status
Undocumented.
Alternatives
St7SetPlateEdgeRadiation2.
St7SetBrickSupport1
Status
Undocumented.
Alternatives
St7SetBrickSupport1F.


St7SetBrickPreStress3
Status
Undocumented.
Alternatives
St7SetBrickPreLoad3.
St7SetBrickNSMass2
Status
Undocumented.
Alternatives
St7SetBrickNSMass5.
St7EnableLoadCase
Status
Undocumented.
Alternatives
St7EnableLSALoadCase.
St7DisableLoadCase
Status
Undocumented.
Alternatives
St7DisableLSALoadCase.
St7GetLoadCaseStatus
Status
Undocumented.
Alternatives
St7GetLSALoadCaseState.


St7SetLinearBucklingInitialFile
Status
Undocumented.
Alternatives
St7SetLBAInitialFile.
St7GetLinearBucklingInitialFile
Status
Undocumented.
Alternatives
St7GetLBAInitialFile.
St7SetNaturalFrequencyInitialFile
Status
Undocumented.
Alternatives
St7SetNFAInitialFile.
St7GetNaturalFrequencyInitialFile
Status
Undocumented.
Alternatives
St7GetNFAInitialFile.
St7SetNonlinearStaticInitialFile
Status
Undocumented.
Alternatives
St7SetNLAInitialFile.


St7GetNonlinearStaticInitialFile
Status
Undocumented.
Alternatives
St7GetNLAInitialFile.
St7SetTransientInitialConditions
Status
Undocumented.
Alternatives
St7SetTransientInitialConditionsType, St7SetTransientInitialConditionsVectors.
St7GetTransientInitialConditions
Status
Undocumented.
Alternatives
St7GetTransientInitialConditionsType, St7GetTransientInitialConditionsVectors.
St7SetNonlinearTransientInitialFile
Status
Undocumented.
Alternatives
St7SetNTAInitialFile.
St7GetNonlinearTransientInitialFile
Status
Undoumented.
Alternatives
St7GetNTAInitialFile.


St7SetLinearTransientInitialFile
Status
Undocumented.
Alternatives
St7SetLTAInitialFile.
St7GetLinearTransientInitialFile
Status
Undoumented.
Alternatives
St7GetLTAInitialFile.
St7SetTransientHeatInitialFile
Status
Undocumented.
Alternatives
St7SetTHAInitialFile.
St7GetTransientHeatInitialFile
Status
Undocumented.
Alternatives
St7GetTHAInitialFile.
St7SetModalDampingType
Status
Undocumented.
Alternatives
St7SetDampingType.


St7GetModalDampingType
Status
Undocumented.
Alternatives
St7GetDampingType.
St7SetHarmonicRange
Status
Undocumented.
Alternatives
St7SetHRARange.
St7GetHarmonicRange
Status
Undocumented.
Alternatives
St7GetHRARange.
St7SetHeatLoadCase
Status
Undocumented.
Alternatives
St7EnableHeatLoadCase.
St7GetHarmonicBaseVector
Status
Undocumented.
Alternatives
St7GetHRABaseVector.


St7SetHarmonicBaseVector
Status
Undocumented.
Alternatives
St7SetHRABaseVector.
St7SetHarmonicLoadType
Status
Undocumented.
Alternatives
St7SetModalLoadType.
St7GetHarmonicLoadType
Status
Undocumented.
Alternatives
St7GetModalLoadType.
St7SetLSAFreedomCase
Status
Undocumented.
Alternatives
Load/Freedom case combinations are not defined explicitly, see
St7EnableLSALoadCase, St7DisableLSALoadCase, St7GetLSALoadCaseState.
St7SetSolverLogicalParameter
Status
Undocumented.
Alternatives
St7SetSolverDefaultsLogical.


St7GetSolverLogicalParameter
Status
Undocumented.
Alternatives
St7GetSolverDefaultsLogical.
St7SetSolverIntegerParameter
Status
Undocumented.
Alternatives
St7SetSolverDefaultsInteger.
St7GetSolverIntegerParameter
Status
Undocumented.
Alternatives
St7GetSolverDefaultsInteger.
St7SetSolverDoubleParameter
Status
Undocumented.
Alternatives
St7SetSolverDefaultsDouble.
St7GetSolverDoubleParameter
Status
Undocumented.
Alternatives
St7GetSolverDefaultsDouble.


St7GetAttribute
Status
Undocumented.
Alternatives
Specific Set/Get functions are now available for all attribute types.
St7GetAttributeID
Status
Undocumented.
Alternatives
Specific Set/Get functions are now available for all attribute types.
St7GetElementGroup
Status
Undocumented.
Alternatives
St7GetEntityGroup.
St7SetElementGroup
Status
Undocumented.
Alternatives
St7SetEntityGroup.
St7DeleteAttributeID
Status
Undocumented.
Alternatives
St7DeleteAttribute.


St7NewTable
Status
Not supported.
Alternatives
St7GetNumTables, St7GetTableInfoByIndex.
St7DeleteTable
Status
Not supported.
Alternatives
St7DeleteTableType.
St7GetTableType
Status
Not supported.
Alternatives
None. The type of all tables is now explicit.
St7GetTableName
Status
Not supported.
Alternatives
St7GetTableTypeName.
St7GetNumTableRows
Status
Not supported.
Alternatives
St7GetNumTableTypeRows.


St7GetTableData
Status
Not supported.
Alternatives
St7GetTableTypeData.
St7SetTableData
Status
Not supported.
Alternatives
St7SetTableTypeData.
St7SetLinkData
Status
Undocumented.
Alternatives
Specific Set/Get functions are now available for all link types.
St7GetLinkData
Status
Undocumented.
Alternatives
Specific Set/Get functions are now available for all link types.
St7SetLinkDoubles
Status
Undocumented.
Alternatives
Specific Set/Get functions are now available for all link types.
