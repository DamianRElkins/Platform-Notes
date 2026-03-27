# Methodology for extracting EXIOBASE Multipliers

## EXIOBASE Version

Multipliers are taken from EXIOBASE V3.6.

## EXIOBASE Conversion

Spend rates are converted using a standard multiplier of €1.1579/£

## Multipliers Used

EXIOBASE multipliers are split between specific quantities of emissions and effective impacts.

Specific quantities (satellite) detail many individual pollutants, land use types, extraction etc.

These quantities feed into characterization factors to create hybrid measures which combine many different quantities of impact into single effective impacts.

Effective impact units like CO2e, PDF, DALY, and combined land and water usage are used to get more readable quantified impacts.

On the platform we display these effective impact units.

## IW+

We use Impact World + characterization factors with EXIOBASE to calculate PDF.km2.year. These characterization factors map to the specific satellite emissions. By treating these as 2 matrices and performing a dot product, we get the PDF multipliers in terms of PDF.m2.year/£ then divide by 1e6 to get PDF.km2.year.
