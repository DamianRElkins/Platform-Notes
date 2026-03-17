# Data Assumptions in the Klere Platform

This document aims to thoroughly catalogue all assumptions made in the processing of data.

## Calculation

### Dependency

The dependency level for an item is determined by 3 things, average materiality, maximum materiality, and the number of relevant dependencies.
The spend weighted dependency level is based on this dependency level and the spend on the given item or group.

#### Materiality Rating

Our dependency system is defined using ENCORE dependency ratings. For each ISIC category ENCORE provides materiality ratings from Very Low - Very High dependency.
These are assigned by Ecosystem Service (ES), so one category will have a set of 25 materiality ratings one for each ES.

Key Assumptions:

- Materiality ratings are linearly mapped to the numbers 1-5 (Very Low = 1 and Very High = 5) and 0 if the rating is N/A or none.
- Where an EXIOBASE category maps to more than one ISIC category, the materiality ratings of that EXIOBASE item are the average of related ISIC category ratings.
- The average materiality is the mean materiality of relevant ES (ES with materiality > 0)
- The maximum materiality is the highest materiality rating of an ES for a given item

#### Number of Dependencies

The number of dependencies related to a category is a basic count of ES that have a materiality score greater than 0 (or equivalently higher than none).

Key Assumptions:

- The number of dependencies is normalized into the 0-5 range using $\frac{25 - \text{Number of related ES}}{25} \times 5$

#### Spend Rating

The spend rating of a group or item is only used in the sidebar. It is meant to highlight which groups or items have the most material dependency. Spend weighting prevents small high dependency groups and items from being ranked above very high spend moderate dependency groups and items.

Key Assumptions:

- The dependency level of the group or item provided is in the 0-5 range.
- The spend weighting is used to scale the level up to a maximum of 5.
- The weighting is defined as below:

$$
a_{min} = \text{Lowest acceptable weight, default }=0.2 \\
a_{max} = \text{Largest acceptable weight, default } = 1.2 \\
\text{spend} = \text{The set of the spend amount of all items/groups depending on if we are weighting an item or a group} \\
s = \text{Spend on the item or group being weighted} \\
\\
f(s) = \frac{\log(s)-\log(\min(\text{spend}))}{\log(\max(\text{spend})) - \log(\min(\text{spend}))} \\
\\
w(s) = a_{min} + f(s) \times (a_{max}-a_{min})
$$

### Final Dependency Score Calculation

The dependency score calculation is based on a [report by the European Commission](https://publications.jrc.ec.europa.eu/repository/bitstream/JRC140003/JRC140003_01.pdf)
