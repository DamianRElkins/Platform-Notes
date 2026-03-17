# Data Assumptions in the Klere Platform

This document aims to thoroughly catalogue all assumptions made in the processing of data.

## Calculation

### Dependency

The dependency level for a group or item (seen in the left sidebar) is determined by 3 things, Materiality, # of dependencies, and spend.

#### Materiality Rating

Our dependency system is defined using ENCORE dependency ratings. For each ISIC category ENCORE provides materiality ratings from Very Low - Very High dependency.
These are assigned by Ecosystem Service (ES), so one category will have a set of 25 materiality ratings one for each ES.

Key Assumptions:

- Materiality ratings are linearly mapped to the numbers 1-5 (Very Low = 1 and Very High = 5) and 0 if the rating is N/A.
- Where an EXIOBASE category maps to more than one ISIC category, the materiality ratings of that EXIOBASE item are the average of related ISIC category ratings.

#### Number of Dependencies

The number of dependencies related to a category is a basic count of ES that have a materiality score greater than 0 (or equivalently higher than none).

Key Assumptions:

- The number of dependencies is normalized into the 0-5 range using $ \frac{25 - \text{# related}}{25} \times 5 $
