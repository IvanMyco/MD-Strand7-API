---
title: "Physical Unit Types"
source: "Strand7 R246 API Manual"
pages: 1017–1019
---

# Physical Unit Types

Title Types

Title Types
The St7GetTitle function call can be used to retrieve information entered in the Model
Information window in Strand7. This includes the model title, author and creation date
entries. The following lists the integer value and title types (as defined in the include and
header files).

- `TITLEModel`

Model title

- `TITLEProject`

Project title

- `TITLEReference`

Reference

- `TITLEAuthor`

Author

- `TITLECreated`

Creation date

- `TITLEModified`

Modification date





Every Strand7 model is described by a unit system accounting for how length, force,
stress, mass, temperature and energy are measured. The St7GetUnits function call can
be used to retrieve the unit system used by the currently open model. This is achieved
with the UnitsArray output parameter. The following includes the position, type (defined
in the include and header files) and unit for each entry in the UnitsArray vector.

- `ipLENGTHU`

Length

- `ipFORCEU`

Force

- `ipSTRESSU`

Stress

- `ipMASSU`

Mass

- `ipTEMPERU`

Temperature

- `ipENERGYU`

Energy

The following lists the value, type (defined in the include and header files) and unit type
available for each unit.

Length

luMETRE

Metre (m)

luCENTIMETRE

Centimetre (cm)

luMILLIMETRE

Millimetre (mm)

luFOOT

Foot (ft)

luINCH

Inch (in)

Force

- `fuNEWTON`

Newton (N)

- `fuKILONEWTON`

Kilonewton (kN)

- `fuMEGANEWTON`

Meganewton (MN)

- `fuKILOFORCE`

Kilogram force (kgf)






- `fuPOUNDFORCE`

Pound force (lbf)

- `fuTONNEFORCE`

Tonne (T)

- `fuKIPFORCE`

Kilopound force (kip)

Stress

- `suPASCAL`

Pascal (Pa)

- `suKILOPASCAL`

Kilopascal (kPa)

- `suMEGAPASCAL`

Megapascal (MPa)

- `suKSCm`

Kilograms force per square centimetre (kgf/cm2)

- `suPSI`

Pounds per square inch (psi)

- `suKSI`

Kilopounds per square inch (ksi)

- `suPSF`

Pounds per square foot (psf)

Mass

- `muKILOGRAM`

Kilogram (kg)

- `muTONNE`

Tonne (t)

- `muGRAM`

Gram (g)

- `muPOUND`

Pound (lb)

- `muSLUG`

Slug (lb.sec2/ft)

Temperature

- `tuCELSIUS`

Celsius (C)

- `tuFAHRENHEIT`

Fahrenheit (F)

- `tuKELVIN`

Kelvin (K)





