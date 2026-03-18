# Data Assumptions in the Klere Platform

This document aims to thoroughly catalogue all assumptions made in the processing of data.

## Dependency

Your dependency is how your operations rely on nature to continue functioning. These dependencies are described by Ecosystem Services which are the benefits nature provides to support or protect business.

### Materiality Rating

Our dependency system is defined using ENCORE dependency ratings. For each ISIC category ENCORE provides materiality ratings from Very Low - Very High dependency.
These are assigned by Ecosystem Service (ES), so one category will have a set of 25 materiality ratings one for each ES.

Key Assumptions:

- Materiality ratings are linearly mapped to the numbers 1-5 (Very Low = 1 and Very High = 5) and 0 if the rating is N/A or none.
- Where an EXIOBASE category maps to more than one ISIC category, the materiality ratings of that EXIOBASE item are the average of related ISIC category ratings.
- The average materiality is the mean materiality of relevant ES (ES with materiality > 0)
- The maximum materiality is the highest materiality rating of an ES for a given item

### Number of Dependencies

The number of dependencies related to a category is a basic count of ES that have a materiality score greater than 0 (or equivalently higher than none).

Key Assumptions:

- The number of dependencies is normalized into the 0-5 range using $\frac{25 - \text{Number of related ES}}{25} \times 5$

### Spend Rating

The spend rating of a group or item is only used in the sidebar. It is meant to highlight which groups or items have the most material dependency. Spend weighting prevents small high dependency groups and items from being ranked above very high spend moderate dependency groups and items.

Key Assumptions:

- The dependency level of the group or item provided is in the 0-5 range.
- The spend weighting is used to scale the level up to a maximum of 5.
- The spend weight is between 0.2 to 1.2 and is on a logarithmic scale.
- The spend-weighted dependency level is the product of the dependency level and the spend weight

### Final Dependency Score Calculation

The dependency score calculation is based on a [report by the European Commission](https://publications.jrc.ec.europa.eu/repository/bitstream/JRC140003/JRC140003_01.pdf)

Key Assumptions:

- It is defined as the mean of the mean materiality, maximum materiality, and normalised count of related ES.
- This will return a score 0-5 which is the dependency score of an item.
- The dependency score of a group is the weighted average of items in the group. Items are weighted by their raw spend.
- The spend weighted dependency score seen in the sidebar is the spend rating $w(s) \times$ Dependency Score.

## Risk

Risk is a measure of the interaction between impact and dependency.

It is based off ENCORE's pressures, ecosystem services, and ecosystem components.

Pressures are ways your activity can impact the natural world.
The intuition is that risk is high where your operations are impacting the aspects of the environment that provide services you depend on.

For example, GHG emissions impact the atmosphere which regulates your local climate which you rely on for stable crop growth.

### Impact and Dependency Scores

For risk, impact and dependency scores are used in three ways.

### Overall Risk Score

The first is the overall risk score. This is a sum of the final impact and dependency scores for a given item or group. These are defined using the same methodology as above.

Key Assumptions:

- Individual Pressures (Impacts) are assigned materiality scores 1-5 (or 0 if there is no material relation) in the same way as dependency.
- Final pressure score is calculated in the same way as the final dependency score above.
- Overall risk score is the sum of final dependency and pressure scores.

### Ecosystem Component Risk

Ecosystem Components are the specific elements of the environment that provide the services we use and can be damaged by our actions.

ENCORE provides us with the relationships between pressures and components and dependencies and components. This describes which ways we may damage the components and what services each component provides.

An example component is water. The Water ecosystem component is all liquid water on earth. ENCORE describes what services are provided by this water and how we can damage this supply.

We quantify risk by Ecosystem Component so you can understand which parts of the natural world you should be most concerned about supporting.

Key Assumptions:

- Individual pressures and dependencies are assigned materiality ratings as above.
- The ecosystem components are assigned component pressure and dependency scores.
  - Pressure and dependency scores are calculated slightly differently than previous.
  - The score is an average of mean materiality, max materiality, \# of related ecosystem services or pressures present, and the \# of related ecosystem services or pressures present relative to the maximum of any ecosystem component
    - Materiality scores are determined exclusively using services or pressures described as related to the ecosystem component by ENCORE
    - The \# of related services or pressures present is the fraction of services or pressures related to the ecosystem component according to ENCORE that have a materiality rating greater than 0.
    - The \# number of related services or pressures present relative to the maximum is the number of services or pressures related to the ecosystem component with a materiality rating greater than 0 divided by the maximum possible number of related services or pressures of any ecosystem component.
      - This serves to prevent ecosystem components that provide fewer services or are more difficult to damage from being too highly scored. This is a proxy for component importance.
      - The maximum possible related services is 19 and the maximum possible related pressures is 11.
- The overall ecosystem component risk score is the sum of the ecosystem component dependency and pressure scores.

### Risk Pathways

Risk pathways are specific interactions between individual pressures and ecosystem services that are concerning.

Risk pathways highlight where high pressures relate strongly to high dependencies through ecosystem components.

An example would be high land use damaging the structural integrity of the environment lessening its ability to prevent floods which your building site relies on for protection.

Key Assumptions:

- Individual pressure and dependencies are assigned mater
